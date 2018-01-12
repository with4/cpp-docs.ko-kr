---
title: CMyProviderWindowsFile | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: cmyproviderwindowsfile
dev_langs: C++
helpviewer_keywords:
- CMyProviderWindowsFile class
- OLE DB providers, wizard-generated files
ms.assetid: 0e9e72ac-1e1e-445f-a7ac-690c20031f9d
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: fef6896df77ff3bcbf9251e2aabba0f810b7f4db
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cmyproviderwindowsfile"></a>CMyProviderWindowsFile
마법사는 데이터의 행을 하나씩 포함 하는 클래스를 만듭니다. 이 경우 호출 됩니다 `CMyProviderWindowsFile`합니다. 다음 코드에 대 한 `CMyProviderWindowsFile` 마법사에서 생성 되 고 사용 하 여 디렉터리에 모든 파일을 나열는 **WIN32_FIND_DATA** 구조입니다. `CMyProviderWindowsFile`상속 되는 **WIN32_FIND_DATA** 구조:  
  
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
  
 `CMyProviderWindowsFile`호출 되는 [사용자 레코드 클래스](../../data/oledb/user-record.md) 공급자의 행 집합의 열을 설명 하는 맵도 포함 하므로 합니다. 공급자 열 맵을 PROVIDER_COLUMN_ENTRY 매크로 사용 하 여 행 집합의 각 필드에 대해 하나의 항목을 포함 합니다. 매크로 이름 열 서 수 이며 및 구조 항목에 대 한 오프셋을 지정합니다. 위의 코드에서 공급자 열 항목 오프셋에 포함 된 **WIN32_FIND_DATA** 구조입니다. 소비자가 호출 하는 경우 **irowset:: Getdata**, 하나의 연속 된 버퍼 데이터를 전송 합니다. 포인터 산술 연산을 수행 하기를 수행 하는 대신 지도 사용 하면 데이터 멤버를 지정할 수 있습니다.  
  
 `CMyProviderRowset` 클래스도 포함 되어는 `Execute` 메서드. `Execute`네이티브 소스에서 데이터를 실제로 읽고 기능입니다. 다음 코드에서는 마법사에서 생성 된 `Execute` 메서드. 이 함수는 Win32 사용 **FindFirstFile** 및 `FindNextFile` 디렉터리의 파일에 대 한 정보를 검색 한 인스턴스의 배치 Api는 `CMyProviderWindowsFile` 클래스입니다.  
  
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
  
 검색할 디렉터리로 나타내는 `m_strCommandText`;를 나타내는 텍스트를 포함 하는이 `ICommandText` 명령 개체에서 인터페이스입니다. 없는 디렉터리를 지정 하는 경우 현재 디렉터리를 사용 합니다.  
  
 메서드 (행에 해당) 각 파일에 대 한 항목을 만들고에 배치 된 **m_rgRowData** 데이터 멤버입니다. `CRowsetImpl` 클래스 정의 **m_rgRowData** 데이터 멤버입니다. 이 배열에 있는 데이터는 전체 테이블을 나타내는 되며 모든 템플릿에서 사용 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [공급자 마법사가 생성하는 파일](../../data/oledb/provider-wizard-generated-files.md)