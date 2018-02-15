---
title: "소비자에 게 반환 동적으로 열 결정 | Microsoft Docs"
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
- bookmarks [C++], dynamically determining columns
- dynamically determining columns [C++]
ms.assetid: 58522b7a-894e-4b7d-a605-f80e900a7f5f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ed7ad9ab7b28758419c2b7c848852678f69bc3e2
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="dynamically-determining-columns-returned-to-the-consumer"></a>소비자에게 반환되는 열을 동적으로 결정
PROVIDER_COLUMN_ENTRY 매크로 정상적으로 처리는 **icolumnsinfo:: Getcolumnsinfo** 호출 합니다. 그러나 소비자는 책갈피를 사용 하도록 선택할 수도, 때문에 공급자는 소비자는 책갈피를 요청 하는 여부에 따라 반환 되는 열을 변경 하려면 수 있어야 합니다.  
  
 처리 하는 **icolumnsinfo:: Getcolumnsinfo** 호출, 삭제 하는 함수를 정의 하는 PROVIDER_COLUMN_MAP `GetColumnInfo`에서 `CAgentMan` 사용자 MyProviderRS.h의 기록 및 직접에 대 한 정의로 바꾸기 `GetColumnInfo` 함수:  
  
```cpp
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
  
 그런 다음 구현는 `GetColumnInfo` 다음 코드에 나와 있는 것 처럼 MyProviderRS.cpp에서 작동 합니다.  
  
 `GetColumnInfo` 먼저 확인 하는 경우 OLE DB 속성인 **DBPROP_BOOKMARKS** 설정 됩니다. 속성을 가져오려면 `GetColumnInfo` 포인터를 사용 하 여 (`pRowset`) 행 집합 개체에 있습니다. `pThis` 포인터는 클래스 속성 맵에 저장 된 클래스는 행 집합을 생성 하는 클래스를 나타냅니다. `GetColumnInfo` 대입문에서 `pThis` 에 대 한 포인터는 `RMyProviderRowset` 포인터입니다.  
  
 확인 하려면는 **DBPROP_BOOKMARKS** 속성을 `GetColumnInfo` 사용 하 여는 `IRowsetInfo` 인터페이스를 호출 하 여 얻을 수 있는 `QueryInterface` 에 `pRowset` 인터페이스입니다. ATL을 사용할 수는 대신 [CComQIPtr](../../atl/reference/ccomqiptr-class.md) 메서드 대신 합니다.  
  
```cpp
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
  
 이 예제에서는 정적 배열을 사용 하 여 열 정보를 포함 하도록 합니다. 소비자는 책갈피 열을 원하지 않는 경우 배열에 있는 하나의 항목을 사용 하지 않습니다. 정보를 처리 하려면 두 배열 매크로 만들면: ADD_COLUMN_ENTRY 및 ADD_COLUMN_ENTRY_EX 합니다. 추가 매개 변수를 사용 하는 ADD_COLUMN_ENTRY_EX `flags`, 즉 책갈피 열을 지정 하는 경우에 필요 합니다.  
  
```cpp
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.h  
  
#define ADD_COLUMN_ENTRY(ulCols, name, ordinal, colSize, type, precision, scale, guid, dataClass, member) \  
   _rgColumns[ulCols].pwszName = (LPOLESTR)name; \  
   _rgColumns[ulCols].pTypeInfo = (ITypeInfo*)NULL; \  
   _rgColumns[ulCols].iOrdinal = (ULONG)ordinal; \  
   _rgColumns[ulCols].dwFlags = 0; \  
   _rgColumns[ulCols].ulColumnSize = (ULONG)colSize; \  
   _rgColumns[ulCols].wType = (DBTYPE)type; \  
   _rgColumns[ulCols].bPrecision = (BYTE)precision; \  
   _rgColumns[ulCols].bScale = (BYTE)scale; \  
   _rgColumns[ulCols].cbOffset = offsetof(dataClass, member);  
  
#define ADD_COLUMN_ENTRY_EX(ulCols, name, ordinal, colSize, type, precision, scale, guid, dataClass, member, flags) \  
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
  
 에 `GetColumnInfo` 책갈피 매크로 함수를 다음과 같이 사용 됩니다.  
  
```  
ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Bookmark"), 0, sizeof(DWORD),  
   DBTYPE_BYTES, 0, 0, GUID_NULL, CAgentMan, dwBookmark,   
   DBCOLUMNFLAGS_ISBOOKMARK)  
```  
  
 이제 컴파일 및 향상 된 공급자를 실행할 수 있습니다. 에 설명 된 대로 공급자를 테스트 하려면 테스트 소비자를 수정 [단순 소비자 구현](../../data/oledb/implementing-a-simple-consumer.md)합니다. 테스트 소비자는 공급자와 함께 실행 합니다. 클릭할 때 테스트 소비자의 공급자에서 적절 한 문자열 검색 있는지 확인 하십시오.는 **실행** 단추는 **테스트 소비자** 대화 상자.  
  
## <a name="see-also"></a>참고 항목  
 [단순한 읽기 전용 공급자의 기능 향상](../../data/oledb/enhancing-the-simple-read-only-provider.md)