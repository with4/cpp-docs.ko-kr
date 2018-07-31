---
title: CMyProviderWindowsFile | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- cmyproviderwindowsfile
dev_langs:
- C++
helpviewer_keywords:
- CMyProviderWindowsFile class
- OLE DB providers, wizard-generated files
ms.assetid: 0e9e72ac-1e1e-445f-a7ac-690c20031f9d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0f18f5a524cbfbfa7f17dfd3964c68329bc8a042
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39338508"
---
# <a name="cmyproviderwindowsfile"></a>CMyProviderWindowsFile
마법사는 데이터의 행을 하나씩 포함 하는 클래스를 만듭니다. 이 경우에 호출 됩니다 `CMyProviderWindowsFile`합니다. 다음 코드에 대 한 `CMyProviderWindowsFile` 마법사에서 생성 되 고 사용 하 여 디렉터리의 모든 파일을 나열 합니다 `WIN32_FIND_DATA` 구조입니다. `CMyProviderWindowsFile` 상속 되는 `WIN32_FIND_DATA` 구조:  
  
```cpp
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
  
 `CMyProviderWindowsFile` 호출 되는 [사용자 레코드 클래스](../../data/oledb/user-record.md) 공급자의 행 집합의 열을 설명 하는 맵도 포함 하므로 합니다. 공급자 열 지도 PROVIDER_COLUMN_ENTRY 매크로 사용 하 여 행 집합의 각 필드에 대해 하나의 항목을 포함 합니다. 매크로 열 이름, 서 수 및 항목을 구조에 오프셋을 지정합니다. 위의 코드에서 공급자 열 항목에 오프셋을 포함 합니다 `WIN32_FIND_DATA` 구조입니다. 소비자가 호출 하는 경우 `IRowset::GetData`, 하나의 연속 된 버퍼에서 데이터를 전송 합니다. 포인터 산술 연산을 수행 하면 작업을 수행 하는 대신 지도 사용 하면 데이터 멤버를 지정할 수 있습니다.  
  
 `CMyProviderRowset` 클래스도 포함 된 `Execute` 메서드. `Execute` 네이티브 소스에서 데이터를 실제로 읽고 무엇 이며 다음 코드에서는 마법사에서 생성 된 `Execute` 메서드. 함수는 Win32를 사용 `FindFirstFile` 하 고 `FindNextFile` 디렉터리의 파일에 대 한 정보를 검색 한 인스턴스의에 배치 하는 Api는 `CMyProviderWindowsFile` 클래스입니다.  
  
```cpp
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
  
 디렉터리를 검색 하 여 표시 됩니다 `m_strCommandText`; 나타내는 텍스트를 포함 합니다 `ICommandText` 명령 개체의 인터페이스입니다. 디렉터리가 없는 지정 된 경우 현재 디렉터리를 사용 합니다.  
  
 메서드 (행에 해당) 각 파일에 대해 하나의 항목을 생성 하 고에 배치 된 `m_rgRowData` 데이터 멤버입니다. 합니다 `CRowsetImpl` 클래스 정의 `m_rgRowData` 데이터 멤버입니다. 이 배열에 있는 데이터 전체 테이블을 나타내며 템플릿 전체에서 사용 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [공급자 마법사가 생성하는 파일](../../data/oledb/provider-wizard-generated-files.md)