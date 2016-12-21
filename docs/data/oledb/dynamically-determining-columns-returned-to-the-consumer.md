---
title: "소비자에게 반환되는 열을 동적으로 결정 | Microsoft Docs"
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
  - "책갈피[C++], 동적으로 열 결정"
  - "동적으로 열 결정[C++]"
ms.assetid: 58522b7a-894e-4b7d-a605-f80e900a7f5f
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 소비자에게 반환되는 열을 동적으로 결정
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

PROVIDER\_COLUMN\_ENTRY 매크로는 일반적으로 **IColumnsInfo::GetColumnsInfo** 호출을 처리합니다.  그러나 소비자는 책갈피를 사용하도록 선택할 수도 있으므로 공급자는 소비자가 책갈피를 요청하는지 여부에 따라 반환되는 열을 변경할 수 있어야 합니다.  
  
 **IColumnsInfo::GetColumnsInfo** 호출을 처리하려면 MyProviderRS.h의 `CAgentMan` 사용자 레코드에서 `GetColumnInfo` 함수를 정의하는 PROVIDER\_COLUMN\_MAP을 삭제하고 이를 사용자의 `GetColumnInfo` 함수에 대한 정의로 바꿉니다.  
  
```  
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.H  
class CAgentMan  
{  
public:  
   DWORD dwBookmark;  
   TCHAR szCommand[256];  
   TCHAR szText[256];  
   TCHAR szCommand2[256];  
   TCHAR szText2[256];  
  
   static ATLCOLUMNINFO* GetColumnInfo(void* pThis, ULONG* pcCols);  
   bool operator==(const CAgentMan& am)  
   {  
      return (lstrcmpi(szCommand, am.szCommand) == 0);  
   }  
  
};  
```  
  
 그런 다음 다음의 코드와 같이 MyProviderRS.cpp에 `GetColumnInfo` 함수를 구현합니다.  
  
 `GetColumnInfo`는 먼저 **DBPROP\_BOOKMARKS** OLE DB 속성이 설정되었는지 확인합니다.  `GetColumnInfo`는 이 속성을 가져오기 위해 행 집합 개체에 대한 포인터\(`pRowset`\)를 사용합니다.  `pThis` 포인터는 행 집합을 만든 클래스를 나타내고, 이 클래스는 속성 맵이 저장된 클래스입니다.  `GetColumnInfo`는 `pThis` 포인터를 `RMyProviderRowset` 포인터로 변환합니다.  
  
 `GetColumnInfo`는 **DBPROP\_BOOKMARKS** 속성을 확인하기 위해 `IRowsetInfo` 인터페이스를 사용합니다. 이 인터페이스는 `pRowset` 인터페이스에 `QueryInterface`를 호출하여 확보할 수 있습니다.  또는 ATL [CComQIPtr](../../atl/reference/ccomqiptr-class.md) 메서드를 대신 사용해도 됩니다.  
  
```  
////////////////////////////////////////////////////////////////////  
// MyProviderRS.cpp  
ATLCOLUMNINFO* CAgentMan::GetColumnInfo(void* pThis, ULONG* pcCols)  
{  
   static ATLCOLUMNINFO _rgColumns[5];  
   ULONG ulCols = 0;  
  
   // Check the property flag for bookmarks; if it is set, set the zero   
   // ordinal entry in the column map with the bookmark information.  
   CAgentRowset* pRowset = (CAgentRowset*) pThis;  
   CComQIPtr<IRowsetInfo, &IID_IRowsetInfo> spRowsetProps = pRowset;  
  
   CDBPropIDSet set(DBPROPSET_ROWSET);  
   set.AddPropertyID(DBPROP_BOOKMARKS);  
   DBPROPSET* pPropSet = NULL;  
   ULONG ulPropSet = 0;  
   HRESULT hr;  
  
   if (spRowsetProps)  
      hr = spRowsetProps->GetProperties(1, &set, &ulPropSet, &pPropSet);  
  
   if (pPropSet)  
   {  
      CComVariant var = pPropSet->rgProperties[0].vValue;  
      CoTaskMemFree(pPropSet->rgProperties);  
      CoTaskMemFree(pPropSet);  
  
      if (SUCCEEDED(hr) && (var.boolVal == VARIANT_TRUE))  
      {  
         ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Bookmark"), 0, sizeof(DWORD),   
         DBTYPE_BYTES, 0, 0, GUID_NULL, CAgentMan, dwBookmark,   
         DBCOLUMNFLAGS_ISBOOKMARK)  
         ulCols++;  
      }  
   }  
  
   // Next, set the other columns up.  
   ADD_COLUMN_ENTRY(ulCols, OLESTR("Command"), 1, 256, DBTYPE_STR, 0xFF, 0xFF,   
      GUID_NULL, CAgentMan, szCommand)  
   ulCols++;  
   ADD_COLUMN_ENTRY(ulCols, OLESTR("Text"), 2, 256, DBTYPE_STR, 0xFF, 0xFF,   
      GUID_NULL, CAgentMan, szText)  
   ulCols++;  
  
   ADD_COLUMN_ENTRY(ulCols, OLESTR("Command2"), 3, 256, DBTYPE_STR, 0xFF, 0xFF,   
      GUID_NULL, CAgentMan, szCommand2)  
   ulCols++;  
   ADD_COLUMN_ENTRY(ulCols, OLESTR("Text2"), 4, 256, DBTYPE_STR, 0xFF, 0xFF,   
      GUID_NULL, CAgentMan, szText2)  
   ulCols++;  
  
   if (pcCols != NULL)  
      *pcCols = ulCols;  
  
   return _rgColumns;  
}  
```  
  
 이 예제는 정적 배열을 사용하여 열 정보를 포함합니다.  소비자에게 책갈피 열이 필요하지 않는 경우 배열의 항목 하나가 사용되지 않습니다.  이 정보를 처리하려면 ADD\_COLUMN\_ENTRY와 ADD\_COLUMN\_ENTRY\_EX라는 두 배열 매크로를 만듭니다.  ADD\_COLUMN\_ENTRY\_EX는 책갈피 열을 지정할 경우 필요한 `flags`라는 추가 매개 변수를 가져옵니다.  
  
```  
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.h  
  
#define ADD_COLUMN_ENTRY(ulCols, name, ordinal, colSize, type, precision,   
scale, guid, dataClass, member) \  
   _rgColumns[ulCols].pwszName = (LPOLESTR)name; \  
   _rgColumns[ulCols].pTypeInfo = (ITypeInfo*)NULL; \  
   _rgColumns[ulCols].iOrdinal = (ULONG)ordinal; \  
   _rgColumns[ulCols].dwFlags = 0; \  
   _rgColumns[ulCols].ulColumnSize = (ULONG)colSize; \  
   _rgColumns[ulCols].wType = (DBTYPE)type; \  
   _rgColumns[ulCols].bPrecision = (BYTE)precision; \  
   _rgColumns[ulCols].bScale = (BYTE)scale; \  
   _rgColumns[ulCols].cbOffset = offsetof(dataClass, member);  
  
#define ADD_COLUMN_ENTRY_EX(ulCols, name, ordinal, colSize, type,   
precision, scale, guid, dataClass, member, flags) \  
   _rgColumns[ulCols].pwszName = (LPOLESTR)name; \  
   _rgColumns[ulCols].pTypeInfo = (ITypeInfo*)NULL; \  
   _rgColumns[ulCols].iOrdinal = (ULONG)ordinal; \  
   _rgColumns[ulCols].dwFlags = flags; \  
   _rgColumns[ulCols].ulColumnSize = (ULONG)colSize; \  
   _rgColumns[ulCols].wType = (DBTYPE)type; \  
   _rgColumns[ulCols].bPrecision = (BYTE)precision; \  
   _rgColumns[ulCols].bScale = (BYTE)scale; \  
   _rgColumns[ulCols].cbOffset = offsetof(dataClass, member); \  
   memset(&(_rgColumns[ulCols].columnid), 0, sizeof(DBID)); \  
   _rgColumns[ulCols].columnid.uName.pwszName = (LPOLESTR)name;  
```  
  
 `GetColumnInfo` 함수에서 책갈피 매크로는 다음과 같이 사용됩니다.  
  
```  
ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Bookmark"), 0, sizeof(DWORD),  
   DBTYPE_BYTES, 0, 0, GUID_NULL, CAgentMan, dwBookmark,   
   DBCOLUMNFLAGS_ISBOOKMARK)  
```  
  
 이제 향상된 공급자를 컴파일하고 실행할 수 있습니다.  공급자를 테스트하려면 [단순 소비자 구현](../../data/oledb/implementing-a-simple-consumer.md)에서 설명하는 대로 테스트 소비자를 수정합니다.  공급자와 함께 테스트 소비자를 실행합니다.  **Test Consumer** 대화 상자의 **Run** 단추를 클릭하여 테스트 소비자가 공급자에서 적절한 문자열을 검색하는지 확인합니다.  
  
## 참고 항목  
 [단순한 읽기 전용 공급자의 기능 향상](../../data/oledb/enhancing-the-simple-read-only-provider.md)