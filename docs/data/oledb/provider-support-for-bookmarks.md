---
title: "공급자의 책갈피 지원 | Microsoft Docs"
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
- IRowsetLocate class, provider support for bookmarks
- OLE DB provider templates, bookmarks
- bookmarks, OLE DB
- IRowsetLocate class
- OLE DB providers, bookmark support
ms.assetid: 1b14ccff-4f76-462e-96ab-1aada815c377
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9e69f0cd9b77f4d492e5011a6c8e653515ea784e
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="provider-support-for-bookmarks"></a>공급자의 책갈피 지원
추가 하는이 항목의 예제는 `IRowsetLocate` 인터페이스는 `CMyProviderRowset` 클래스입니다. 대부분의 경우 기존 COM 개체에는 인터페이스를 추가 하 여 시작 합니다. 소비자 템플릿에서 많은 호출을 추가 하 여 테스트할 수 있습니다. 예제에 나오는 하는 방법:  
  
-   공급자에 인터페이스를 추가 합니다.  
  
-   소비자에 게 반환할 열을 결정 합니다.  
  
-   책갈피 지원을 추가 합니다.  
  
 `IRowsetLocate` 인터페이스는 `IRowset` 인터페이스에서 상속됩니다. 추가 하는 `IRowsetLocate` 인터페이스, 상속 `CMyProviderRowset` 에서 [IRowsetLocateImpl](../../data/oledb/irowsetlocateimpl-class.md)합니다.  
  
 추가 `IRowsetLocate` 인터페이스는 대부분의 인터페이스에서 약간 다릅니다. 하려면 vtable, OLE DB 공급자 템플릿은 파생된 된 인터페이스를 처리 하는 템플릿 매개 변수를 보유 합니다. 다음 코드에는 새 상속 목록을 보여 줍니다.  
  
```cpp
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.h  
  
// CMyProviderRowset  
class CMyProviderRowset : public CRowsetImpl< CMyProviderRowset,   
      CTextData, CMyProviderCommand, CAtlArray<CTextData>,   
      CSimpleRow,   
          IRowsetLocateImpl<CMyProviderRowset, IRowsetLocate>>  
```  
  
 네 번째, 다섯 번째 및 여섯 번째 매개 변수 모두 추가 됩니다. 이 예제에서는 네 번째 작업에 대 한 기본값을 사용 하 고 5 번째 매개 변수를 지정 하지만 `IRowsetLocateImpl` 여섯 번째 매개 변수로 합니다. `IRowsetLocateImpl` 두 개의 템플릿 매개 변수를 사용 하는 OLE DB 템플릿 클래스: 이러한 연결는 `IRowsetLocate` 인터페이스는 `CMyProviderRowset` 클래스. 대부분의 인터페이스를 추가 하려면이 단계는 하 한 다음 이동할 수 있습니다. 만 `IRowsetLocate` 및 `IRowsetScroll` 인터페이스에서 이러한 방식으로 처리 해야 합니다.  
  
 다음 지시 해야는 `CMyProviderRowset` 호출할 `QueryInterface` 에 대 한는 `IRowsetLocate` 인터페이스입니다. 줄 추가 `COM_INTERFACE_ENTRY(IRowsetLocate)` 맵에 있습니다. 에 대 한 인터페이스 맵을 `CMyProviderRowset` 다음 코드와 같이 표시 됩니다.  
  
```cpp
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.h  
  
typedef CRowsetImpl< CMyProviderRowset, CTextData, CMyProviderCommand, CAtlArray<CTextData>, CSimpleRow, IRowsetLocateImpl<CMyProviderRowset, IRowsetLocate>> _RowsetBaseClass;  
  
BEGIN_COM_MAP(CMyProviderRowset)  
   COM_INTERFACE_ENTRY(IRowsetLocate)  
   COM_INTERFACE_ENTRY_CHAIN(_RowsetBaseClass)  
END_COM_MAP()  
```  
  
 지도에 후크 해야는 `CRowsetImpl` 클래스입니다. 에 후크 할 COM_INTERFACE_ENTRY_CHAIN 매크로에 추가 `CRowsetImpl` 지도입니다. 또한 호출 형식 정의 만든 `RowsetBaseClass` 상속 정보 구성 됩니다. 이 임의의 형식 정의와 무시 될 수 있습니다.  
  
 마지막으로 처리는 **icolumnsinfo:: Getcolumnsinfo** 호출 합니다. 일반적으로이 작업을 수행 하려면 PROVIDER_COLUMN_ENTRY 매크로 사용 합니다. 하지만, 소비자는 책갈피를 사용 해야 할 수 있습니다. 소비자는 책갈피를 요청 하는 여부에 따라 공급자를 반환 하는 열을 변경할 수 있어야 합니다.  
  
 처리 하는 **icolumnsinfo:: Getcolumnsinfo** 호출, 삭제는 **PROVIDER_COLUMN** 에 매핑하는 `CTextData` 클래스입니다. 함수를 정의 하는 PROVIDER_COLUMN_MAP 매크로 `GetColumnInfo`합니다. 정의 하면 사용자 고유의 `GetColumnInfo` 함수입니다. 함수 선언은 다음과 같이 표시 됩니다.  
  
```cpp
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.H  
  
class CTextData  
{  
   ...  
     // NOTE: Be sure you removed the PROVIDER_COLUMN_MAP!  
   static ATLCOLUMNINFO* GetColumnInfo(CMyProviderRowset* pThis,   
        ULONG* pcCols);  
   static ATLCOLUMNINFO* GetColumnInfo(CMyProviderCommand* pThis,   
        ULONG* pcCols);  
...  
};  
```  
  
 그런 다음 구현는 `GetColumnInfo` MyProviderRS.cpp 파일에서 다음과 같이 작동 합니다.  
  
```cpp
////////////////////////////////////////////////////////////////////  
// MyProviderRS.cpp  
  
template <class TInterface>  
ATLCOLUMNINFO* CommonGetColInfo(IUnknown* pPropsUnk, ULONG* pcCols)  
{  
   static ATLCOLUMNINFO _rgColumns[5];  
   ULONG ulCols = 0;  
  
   CComQIPtr<TInterface> spProps = pPropsUnk;  
  
   CDBPropIDSet set(DBPROPSET_ROWSET);  
   set.AddPropertyID(DBPROP_BOOKMARKS);  
   DBPROPSET* pPropSet = NULL;  
   ULONG ulPropSet = 0;  
   HRESULT hr;  
  
   if (spProps)  
      hr = spProps->GetProperties(1, &set, &ulPropSet, &pPropSet);  
  
   // Check the property flag for bookmarks, if it is set, set the   
// zero ordinal entry in the column map with the bookmark   
// information.  
  
   if (pPropSet)  
   {  
      CComVariant var = pPropSet->rgProperties[0].vValue;  
      CoTaskMemFree(pPropSet->rgProperties);  
      CoTaskMemFree(pPropSet);  
  
      if ((SUCCEEDED(hr) && (var.boolVal == VARIANT_TRUE)))  
      {  
         ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Bookmark"), 0,   
                     sizeof(DWORD), DBTYPE_BYTES,  
            0, 0, GUID_NULL, CAgentMan, dwBookmark,         
                        DBCOLUMNFLAGS_ISBOOKMARK)  
         ulCols++;  
      }  
  
   }  
  
   // Next set the other columns up.  
   ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Field1"), 1, 16, DBTYPE_STR,   
          0xFF, 0xFF, GUID_NULL, CTextData, szField1)  
   ulCols++;  
   ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Field2"), 2, 16, DBTYPE_STR,  
       0xFF, 0xFF, GUID_NULL, CTextData, szField2)  
   ulCols++;  
  
   if (pcCols != NULL)  
      *pcCols = ulCols;  
  
   return _rgColumns;  
}  
  
ATLCOLUMNINFO* CTextData::GetColumnInfo(CMyProviderCommand* pThis,   
     ULONG* pcCols)  
{  
   return CommonGetColInfo<ICommandProperties>(pThis->GetUnknown(),  
        pcCols);  
}  
  
ATLCOLUMNINFO* CAgentMan::GetColumnInfo(RUpdateRowset* pThis, ULONG* pcCols)  
{  
   return CommonGetColInfo<IRowsetInfo>(pThis->GetUnknown(), pcCols);  
}  
```  
  
 `GetColumnInfo` 이라는 속성 있는지 여부를 확인 하려면 첫 번째 확인 **DBPROP_IRowsetLocate** 설정 됩니다. OLE DB의 각 행 집합 개체는 선택적 인터페이스에 대 한 속성이 있습니다. 소비자가 이러한 선택적 인터페이스 중 하나를 사용 하려는 경우에 속성이 true로 설정 합니다. 공급자 수이 속성을 선택 하 고에 따라 특별 한 조치를 취합니다.  
  
 구현에 명령 개체에 대 한 포인터를 사용 하 여 속성을 가져옵니다. `pThis` 포인터 행 집합이 나 명령 클래스를 나타냅니다. 로이 작업에 전달 해야 하는 여기서 서식 파일을 사용 하므로 `void` 포인터 또는 코드는 컴파일되지 않습니다.  
  
 열 정보를 포함 하도록 정적 배열을 지정 합니다. 소비자는 책갈피 열을 원하지 않는 경우 배열에 항목이 낭비 됩니다. 이 배열에 동적으로 할당할 수 있지만 제대로 소멸 되었는지 확인 해야 합니다. 이 예제에서는 정의 하 고 배열에 정보를 삽입 하는 ADD_COLUMN_ENTRY 및 ADD_COLUMN_ENTRY_EX 매크로 사용 합니다. 다음 코드에 나와 있는 것 처럼 MyProviderRS.H 파일에 매크로 추가할 수 있습니다.  
  
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
  
 소비자의 코드를 테스트 하려면 몇 가지 변경에 `OnRun` 처리기입니다. 함수에 첫 번째 변경 내용이 속성은 속성 집합을 추가 하는 코드를 추가 합니다. 코드 집합은 **DBPROP_IRowsetLocate** 속성을 true로, 따라서 공급자 라는 책갈피 열이 필요 합니다. `OnRun` 처리기 코드는 다음과 같이 나타납니다.  
  
```cpp
//////////////////////////////////////////////////////////////////////  
// TestProv Consumer Application in TestProvDlg.cpp  
  
void CTestProvDlg::OnRun()   
{  
   CCommand<CAccessor<CProvider>> table;  
   CDataSource source;  
   CSession   session;  
  
   if (source.Open("MyProvider.MyProvider.1", NULL, NULL, NULL,   
          NULL) != S_OK)  
      return;  
  
   if (session.Open(source) != S_OK)  
      return;  
  
   CDBPropSet propset(DBPROPSET_ROWSET);  
   propset.AddProperty(DBPROP_IRowsetLocate, true);  
   if (table.Open(session, _T("c:\\public\\testprf2\\myData.txt"),   
          &propset) != S_OK)  
      return;  
  
   CBookmark<4> tempBookmark;  
   ULONG ulCount=0;  
   while (table.MoveNext() == S_OK)  
   {  
  
      DBCOMPARE compare;  
      if (ulCount == 2)  
         tempBookmark = table.bookmark;  

HRESULT hr = table.Compare(table.dwBookmark, table.dwBookmark,  
                 &compare);  
      if (FAILED(hr))  
         ATLTRACE(_T("Compare failed: 0x%X\n"), hr);  
      else  
         _ASSERTE(compare == DBCOMPARE_EQ);  
  
      m_ctlString1.AddString(table.szField1);  
      m_ctlString2.AddString(table.szField2);  
      ulCount++;  
   }  
  
   table.MoveToBookmark(tempBookmark);  
   m_ctlString1.AddString(table.szField1);  
   m_ctlString2.AddString(table.szField2);  
}  
```  
  
 While 루프 포함 코드를 호출할 수는 `Compare` 에서 메서드는 `IRowsetLocate` 인터페이스입니다. 코드를 정확히 동일한 책갈피를 비교 하기 때문에 항상 전달 해야 합니다. 또한 하나의 책갈피가 임시 변수에 저장 while 후 사용할 수 있도록 루프를 호출 하는 완료는 `MoveToBookmark` 소비자 템플릿 함수입니다. `MoveToBookmark` 함수 호출의 `GetRowsAt` 메서드에서 `IRowsetLocate`합니다.  
  
 소비자의 사용자 레코드를 업데이트 해야 할 수도 있습니다. 항목 책갈피 및에서 항목을 처리 하는 클래스에 추가 하는 **COLUMN_MAP**:  
  
```cpp
///////////////////////////////////////////////////////////////////////  
// TestProvDlg.cpp  
  
class CProvider  
{  
// Attributes  
public:  
   CBookmark<4>    bookmark;  // Add this line  
   char   szCommand[16];  
   char   szText[256];  
  
   // Binding Maps  
BEGIN_ACCESSOR_MAP(CProvider, 1)  
   BEGIN_ACCESSOR(0, true)   // auto accessor  
      BOOKMARK_ENTRY(bookmark)  // Add this line  
      COLUMN_ENTRY(1, szField1)  
      COLUMN_ENTRY(2, szField2)  
   END_ACCESSOR()  
END_ACCESSOR_MAP()  
};  
```  
  
 작성 하 고 사용 하 여 공급자를 실행 하는 수 있어야 코드를 업데이트 하는 경우는 `IRowsetLocate` 인터페이스입니다.  
  
## <a name="see-also"></a>참고 항목  
 [고급 공급자 기술](../../data/oledb/advanced-provider-techniques.md)