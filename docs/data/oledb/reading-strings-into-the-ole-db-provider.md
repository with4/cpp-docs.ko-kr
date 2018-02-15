---
title: "OLE DB 공급자로 문자열 읽어들이기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, reading strings into
ms.assetid: 517f322c-f37e-4eed-bf5e-dd9a412c2f98
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b57c9e9a71e8a0b603207a095e2bede333ed6ed6
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="reading-strings-into-the-ole-db-provider"></a>OLE DB 공급자로 문자열 읽어들이기
`RMyProviderRowset::Execute` 함수에서 파일을 열고 문자열 읽습니다. 소비자는 공급자에 파일 이름을 호출 하 여 전달 [icommandtext:: Setcommandtext](https://msdn.microsoft.com/en-us/library/ms709757.aspx)합니다. 공급자 파일의 이름을 받는 멤버 변수에 저장 합니다. `m_szCommandText`합니다. `Execute` 파일 이름을 읽고 `m_szCommandText`합니다. 파일 이름이 잘못 되었거나 파일 언어가 없는 경우 `Execute` 에서 오류를 반환 합니다. 을 열고 파일 및 호출 `fgets` 문자열을 검색 합니다. 각 문자열 집합에, 읽기에 대 한 `Execute` 사용자 레코드의 인스턴스를 만듭니다 (`CAgentMan`) 배열에 넣습니다.  
  
 파일을 열 수 없는 경우 `Execute` 반환 해야 **DB_E_NOTABLE**합니다. 반환 하는 경우 **E_FAIL** 공급자 많은 소비자와 함께 작동 하지 않으며 OLE DB를 통과 하지 못하는 대신 [규칙 테스트](../../data/oledb/testing-your-provider.md)합니다.  
  
## <a name="example"></a>예  
  
### <a name="description"></a>설명  
 편집한 `Execute` 함수는 다음과 같습니다.  
  
### <a name="code"></a>코드  
  
```cpp
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
  
## <a name="see-also"></a>참고 항목  
 [단순한 읽기 전용 공급자 구현](../../data/oledb/implementing-the-simple-read-only-provider.md)