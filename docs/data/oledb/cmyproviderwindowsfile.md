---
title: "CMyProviderWindowsFile | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "cmyproviderwindowsfile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMyProviderWindowsFile 클래스"
  - "OLE DB 공급자, 마법사에서 생성된 파일"
ms.assetid: 0e9e72ac-1e1e-445f-a7ac-690c20031f9d
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# CMyProviderWindowsFile
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

마법사는 데이터 행 하나를 포함하는 클래스를 만들고, 여기에서는 이 클래스를 `CMyProviderWindowsFile`이라고 합니다.  다음의 `CMyProviderWindowsFile` 코드는 마법사가 생성한 것으로 **WIN32\_FIND\_DATA** 구조를 사용하여 디렉터리에 있는 모든 파일을 나열합니다.  `CMyProviderWindowsFile`은 **WIN32\_FIND\_DATA** 구조에서 상속합니다.  
  
```  
/////////////////////////////////////////////////////////////////////  
// MyProviderRS.H  
  
class CMyProviderWindowsFile:   
   public WIN32_FIND_DATA  
{  
public:  
BEGIN_PROVIDER_COLUMN_MAP(CMyProviderWindowsFile)  
   PROVIDER_COLUMN_ENTRY("FileAttributes", 1, dwFileAttributes)  
   PROVIDER_COLUMN_ENTRY("FileSizeHigh", 2, nFileSizeHigh)  
   PROVIDER_COLUMN_ENTRY("FileSizeLow", 3, nFileSizeLow)  
   PROVIDER_COLUMN_ENTRY_STR("FileName", 4, cFileName)  
   PROVIDER_COLUMN_ENTRY_STR("AltFileName", 5, cAlternateFileName)  
END_PROVIDER_COLUMN_MAP()  
};  
```  
  
 `CMyProviderWindowsFile`은 공급자 행 집합의 열을 설명하는 맵도 포함하므로 [사용자 레코드 클래스](../../data/oledb/user-record.md)라고 합니다.  공급자의 열 맵은 PROVIDER\_COLUMN\_ENTRY 매크로를 사용하여 행 집합의 각 필드에 대한 항목을 하나씩 포함합니다.  이 매크로는 열 이름, 서수 및 구조 항목에 대한 오프셋을 지정합니다.  위 코드의 공급자 열 항목에는 **WIN32\_FIND\_DATA** 구조에 대한 오프셋이 포함되어 있습니다.  소비자가 **IRowset::GetData**를 호출하면 데이터가 하나의 연속 버퍼로 전송됩니다.  맵은 사용자가 포인터 산술 연산을 수행하지 않고 대신 데이터 멤버를 지정할 수 있도록 합니다.  
  
 `CMyProviderRowset` 클래스에는 `Execute` 메서드도 포함되어 있습니다.  `Execute`는 네이티브 소스에서 실제로 데이터를 읽어 들이는 역할을 합니다.  다음 코드는 마법사가 생성한 `Execute` 메서드를 보여 줍니다.  이 함수는 Win32 **FindFirstFile**과 `FindNextFile` API를 사용하여 디렉터리의 파일에 대한 정보를 검색하고 `CMyProviderWindowsFile` 클래스의 인스턴스에 이 정보를 놓습니다.  
  
```  
/////////////////////////////////////////////////////////////////////  
// MyProviderRS.H  
  
HRESULT Execute(DBPARAMS * pParams, LONG* pcRowsAffected)  
{  
   USES_CONVERSION;  
   BOOL bFound = FALSE;  
   HANDLE hFile;  
   LPTSTR  szDir = (m_strCommandText == _T("")) ? _T("*.*") :  
       OLE2T(m_strCommandText);  
   CMyProviderWindowsFile wf;  
   hFile = FindFirstFile(szDir, &wf);  
   if (hFile == INVALID_HANDLE_VALUE)  
      return DB_E_ERRORSINCOMMAND;  
   LONG cFiles = 1;  
   BOOL bMoreFiles = TRUE;  
   while (bMoreFiles)  
   {  
      if (!m_rgRowData.Add(wf))  
         return E_OUTOFMEMORY;  
      bMoreFiles = FindNextFile(hFile, &wf);  
      cFiles++;  
   }  
   FindClose(hFile);  
   if (pcRowsAffected != NULL)  
      *pcRowsAffected = cFiles;  
   return S_OK;  
}  
```  
  
 검색할 디렉터리는 `m_strCommandText`로 나타나고, 여기에는 명령 개체의 `ICommandText` 인터페이스가 나타내는 텍스트가 포함됩니다.  디렉터리를 지정하지 않으면 현재 디렉터리를 사용합니다.  
  
 이 메서드는 행에 해당하는 각 파일에 대해 항목을 하나씩 만든 다음 항목을 **m\_rgRowData** 데이터 멤버에 놓습니다.  `CRowsetImpl` 클래스는 **m\_rgRowData** 데이터 멤버를 정의합니다.  이 배열의 데이터는 전체 테이블을 나타내며 모든 템플릿에서 사용됩니다.  
  
## 참고 항목  
 [공급자 마법사가 생성하는 파일](../../data/oledb/provider-wizard-generated-files.md)