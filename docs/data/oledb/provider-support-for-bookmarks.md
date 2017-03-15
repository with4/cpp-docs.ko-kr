---
title: "공급자의 책갈피 지원 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "책갈피, OLE DB"
  - "IRowsetLocate 클래스"
  - "IRowsetLocate 클래스, 공급자의 책갈피 지원"
  - "OLE DB 공급자 템플릿, 책갈피"
  - "OLE DB 공급자, 책갈피 지원"
ms.assetid: 1b14ccff-4f76-462e-96ab-1aada815c377
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 공급자의 책갈피 지원
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목의 예제는 `CMyProviderRowset` 클래스에 `IRowsetLocate` 인터페이스를 추가합니다.  대부분의 경우 기존 COM 개체에 인터페이스를 추가하여 시작한 다음  소비자 템플릿의 호출을 추가하여 테스트할 수 있습니다.  예제에서는 다음 방법을 보여 줍니다.  
  
-   공급자에 인터페이스 추가  
  
-   소비자에게 반환할 열을 동적으로 결정  
  
-   책갈피 지원 추가  
  
 `IRowsetLocate` 인터페이스는 `IRowset` 인터페이스에서 상속합니다.  `IRowsetLocate` 인터페이스를 추가하려면 [IRowsetLocateImpl](../../data/oledb/irowsetlocateimpl-class.md)에서 `CMyProviderRowset`을 상속합니다.  
  
 `IRowsetLocate` 인터페이스를 추가하는 것은 대부분의 다른 인터페이스를 추가하는 것과 약간 다릅니다.  VTABLE을 정렬하기 위해 OLE DB 공급자 템플릿에는 파생된 인터페이스를 처리하기 위한 템플릿 매개 변수가 있습니다.  다음 코드는 새로운 상속 목록을 보여 줍니다.  
  
```  
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.h  
  
// CMyProviderRowset  
class CMyProviderRowset : public CRowsetImpl< CMyProviderRowset,   
      CTextData, CMyProviderCommand, CAtlArray<CTextData>,   
      CSimpleRow,   
          IRowsetLocateImpl<CMyProviderRowset, IRowsetLocate> >  
```  
  
 네 번째, 다섯 번째 및 여섯 번째 매개 변수가 모두 추가됩니다.  이 예제에서는 네 번째 및 다섯 번째 매개 변수에 기본값을 사용하지만 여섯 번째 매개 변수로는 `IRowsetLocateImpl`을 지정합니다.  `IRowsetLocateImpl`은 두 개의 템플릿 매개 변수를 사용하는 OLE DB 템플릿 클래스입니다. 이 두 개의 템플릿 매개 변수는 `IRowsetLocate` 인터페이스를 `CMyProviderRowset` 클래스에 후크합니다.  대부분의 인터페이스를 추가할 때는 이 단계를 건너 뛰고 다음 단계로 이동하고,  `IRowsetLocate`과 `IRowsetScroll` 인터페이스만 이런 방법으로 처리하면 됩니다.  
  
 그런 다음 `CMyProviderRowset`에 `IRowsetLocate` 인터페이스에 대해 `QueryInterface`를 호출하라고 알려야 합니다.  맵에 `COM_INTERFACE_ENTRY(IRowsetLocate)` 줄을 추가합니다.  `CMyProviderRowset`에 대한 인터페이스는 다음 코드에 나타난 것과 같습니다.  
  
```  
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.h  
  
typedef CRowsetImpl< CMyProviderRowset, CTextData, CMyProviderCommand, CAtlArray<CTextData>, CSimpleRow, IRowsetLocateImpl<CMyProviderRowset, IRowsetLocate> > _RowsetBaseClass;  
  
BEGIN_COM_MAP(CMyProviderRowset)  
   COM_INTERFACE_ENTRY(IRowsetLocate)  
   COM_INTERFACE_ENTRY_CHAIN(_RowsetBaseClass)  
END_COM_MAP()  
```  
  
 또한 맵을 `CRowsetImpl` 클래스에 후크해야 합니다.  COM\_INTERFACE\_ENTRY\_CHAIN 매크로를 추가하여 `CRowsetImpl` 맵을 후크합니다.  또한 상속 정보로 구성된 `RowsetBaseClass`라는 typedef를 만듭니다.  이 typedef는 임의로 만드는 것으로 무시할 수 있습니다.  
  
 마지막으로 **IColumnsInfo::GetColumnsInfo** 호출을 처리합니다.  일반적으로 PROVIDER\_COLUMN\_ENTRY 매크로를 사용하여 처리하면 되지만,  소비자에서 책갈피를 사용하는 경우도 있습니다.  따라서 소비자가 책갈피를 요청하는지에 따라 공급자가 반환하는 열을 변경할 수 있어야 합니다.  
  
 **IColumnsInfo::GetColumnsInfo** 호출을 처리하려면 `CTextData` 클래스에서 **PROVIDER\_COLUMN** 맵을 삭제합니다.  PROVIDER\_COLUMN\_MAP 매크로는 `GetColumnInfo` 함수를 정의합니다.  사용자 고유의 `GetColumnInfo` 함수를 정의해야 합니다.  이 함수는 다음과 비슷합니다.  
  
```  
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
  
 그런 다음 MyProviderRS.cpp 파일에 다음과 같이 `GetColumnInfo` 함수를 구현합니다.  
  
```  
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
  
 `GetColumnInfo`는 먼저 **DBPROP\_IRowsetLocate** 속성이 설정되어 있는지 확인합니다.  OLE DB에는 행 집합 개체의 각 선택적 인터페이스에 대한 속성이 있습니다.  소비자가 이러한 선택적 인터페이스 중 하나를 사용하려고 하면 해당 속성을 true로 설정합니다.  그런 다음 공급자가 이 속성을 확인하고 설정 여부에 따라 특별한 작업을 수행합니다.  
  
 사용자 구현에서는 명령 개체에 대한 포인터를 사용하여 속성을 가져옵니다.  `pThis` 포인터는 행 집합이나 명령 클래스를 나타냅니다.  여기서는 템플릿을 사용하므로 이 포인터를 `void` 포인터로 전달해야 하며, 이렇게 하지 않으면 코드가 컴파일되지 않습니다.  
  
 열 정보를 포함할 정적 배열을 지정합니다.  소비자가 책갈피 열을 필요로 하지 않을 경우에는 배열의 항목 하나가 낭비됩니다.  이 배열을 동적으로 할당할 수 있지만 그렇게 하려면 할당을 적절히 삭제할 수 있어야 합니다.  이 예제에서는 ADD\_COLUMN\_ENTRY와 ADD\_COLUMN\_ENTRY\_EX 매크로를 정의하고 사용하여 배열에 정보를 삽입합니다.  다음 코드에서와 같이 MyProviderRS.H 파일에 매크로를 추가할 수 있습니다.  
  
```  
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
  
 소비자에서 코드를 테스트하려면 `OnRun` 처리기에 몇 가지 변경을 해야 합니다.  함수에 대해 가장 먼저 변경해야 하는 사항은 속성 집합에 속성을 추가하는 코드를 추가하는 것입니다.  이 코드는 **DBPROP\_IRowsetLocate** 속성을 true로 설정하여 책갈피 열이 필요하다는 것을 공급자에게 알립니다.  `OnRun` 처리기 코드는 다음과 같습니다.  
  
```  
//////////////////////////////////////////////////////////////////////  
// TestProv Consumer Application in TestProvDlg.cpp  
  
void CTestProvDlg::OnRun()   
{  
   CCommand<CAccessor<CProvider> > table;  
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
  
 while 루프에는 `IRowsetLocate` 인터페이스의 `Compare` 메서드를 호출하기 위한 코드가 포함되어 있습니다.  정확히 같은 책갈피를 비교하기 때문에 항상 이 코드를 전달해야 합니다.  또한 while 루프가 소비자 템플릿의 `MoveToBookmark` 함수를 호출하는 것을 마친 후 사용할 수 있도록 임시 변수에 책갈피를 하나 저장합니다.  `MoveToBookmark` 함수는 `IRowsetLocate`의 `GetRowsAt` 메서드를 호출합니다.  
  
 또한 소비자의 사용자 레코드를 업데이트해야 합니다.  책갈피를 처리하는 항목을 클래스에 추가하고 **COLUMN\_MAP**에 항목을 추가합니다.  
  
```  
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
  
 코드를 업데이트한 다음 `IRowsetLocate` 인터페이스를 사용하여 공급자를 빌드하고 실행할 수 있어야 합니다.  
  
## 참고 항목  
 [고급 공급자 기술](../../data/oledb/advanced-provider-techniques.md)