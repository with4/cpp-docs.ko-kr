---
title: "OLE DB 공급자로 문자열 읽어들이기 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OLE DB 공급자, 문자열 읽어들이기"
ms.assetid: 517f322c-f37e-4eed-bf5e-dd9a412c2f98
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OLE DB 공급자로 문자열 읽어들이기
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`RMyProviderRowset::Execute` 함수가 파일을 열고 문자열을 읽습니다.  소비자는 [ICommandText::SetCommandText](https://msdn.microsoft.com/en-us/library/ms709757.aspx)를 호출하여 파일 이름을 공급자에게 전달합니다.  공급자는 파일 이름을 받아 `m_szCommandText` 멤버 변수에 저장하고,  `Execute`가 `m_szCommandText`에서 파일 이름을 읽습니다.  파일 이름이 올바르지 않거나 파일을 사용할 수 없는 경우에는 `Execute`가 오류를 반환합니다.  또는 파일을 열고 `fgets`를 호출하여 문자열을 검색합니다.  `Execute`는 읽은 각 문자열 집합에 대해 사용자 레코드\(`CAgentMan`\)의 인스턴스를 만들어 배열에 넣습니다.  
  
 파일을 열 수 없는 경우에는 `Execute`가 **DB\_E\_NOTABLE**을 반환해야 합니다.  **DB\_E\_NOTABLE**을 반환하지 않고 **E\_FAIL**을 반환하면 공급자가 대부분의 소비자와 작동하지 않게 되어 OLE DB [규칙 테스트](../../data/oledb/testing-your-provider.md)를 통과하지 못합니다.  
  
## 예제  
  
### 설명  
 다음은 `Execute` 함수를 편집한 것입니다.  
  
### 코드  
  
```  
/////////////////////////////////////////////////////////////////////////  
// MyProviderRS.h  
class RMyProviderRowset : public CRowsetImpl< RMyProviderRowset, CAgentMan, CRMyProviderCommand>  
{  
public:  
    HRESULT Execute(DBPARAMS * pParams, LONG* pcRowsAffected)  
    {  
        enum {  
            sizeOfBuffer = 256,  
            sizeOfFile = MAX_PATH  
        };  
        USES_CONVERSION;  
        FILE* pFile = NULL;  
        TCHAR szString[sizeOfBuffer];  
        TCHAR szFile[sizeOfFile];  
        size_t nLength;        errcodeerr;  
  
        ObjectLock lock(this);  
  
        // From a filename, passed in as a command text, scan the file  
        // placing data in the data array.  
        if (!m_szCommandText)  
        {  
            ATLTRACE("No filename specified");  
            return E_FAIL;  
        }  
  
        // Open the file  
        _tcscpy_s(szFile, sizeOfFile, m_szCommandText);  
        if (szFile[0] == _T('\0') ||   
            ((err = fopen_s(&pFile, &szFile[0], "r")) == 0))  
        {  
            ATLTRACE("Could not open file");  
            return DB_E_NOTABLE;  
        }  
  
        // Scan and parse the file.  
        // The file should contain two strings per record  
        LONG cFiles = 0;  
        while (fgets(szString, sizeOfBuffer, pFile) != NULL)  
        {  
            nLength = strnlen(szString, sizeOfBuffer);  
            szString[nLength-1] = '\0';   // Strip off trailing CR/LF  
            CAgentMan am;  
            _tcscpy_s(am.szCommand, am.sizeOfCommand, szString);  
            _tcscpy_s(am.szCommand2, am.sizeOfCommand2, szString);  
  
            if (fgets(szString, sizeOfBuffer, pFile) != NULL)  
            {  
                nLength = strnlen(szString, sizeOfBuffer);  
                szString[nLength-1] = '\0'; // Strip off trailing CR/LF  
                _tcscpy_s(am.szText, am.sizeOfText, szString);  
                _tcscpy_s(am.szText2, am.sizeOfText2, szString);  
            }  
  
            am.dwBookmark = ++cFiles;  
            if (!m_rgRowData.Add(am))  
            {  
                ATLTRACE("Couldn't add data to array");  
                fclose(pFile);  
                return E_FAIL;  
            }  
        }  
  
        if (pcRowsAffected != NULL)  
            *pcRowsAffected = cFiles;  
        return S_OK;  
    }  
}  
```  
  
## 참고 항목  
 [단순한 읽기 전용 공급자 구현](../../data/oledb/implementing-the-simple-read-only-provider.md)