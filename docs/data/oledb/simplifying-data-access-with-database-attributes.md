---
title: 데이터베이스 특성을 가진 데이터 액세스 단순화 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- vc-attr.db_param
- vc-attr.db_column
- vc-attr.db_accessor
- vc-attr.db_command
- vc-attr.db_table
- vc-attr.db_source
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++], database
- attributes [C++], data access
- databases [C++], attributes
- data [C++], simplifying access
- data access [C++], database attributes
- database attributes [C++]
- OLE DB consumers [C++], database attributes
- attributes [C++], OLE DB consumer
ms.assetid: 560d2456-e307-4cb7-ba7b-4d0ed674697f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e665369f292a646353d1a180661982ce4c902665
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33111717"
---
# <a name="simplifying-data-access-with-database-attributes"></a>데이터베이스 특성을 사용하여 데이터 액세스 단순화
이 항목에서는 데이터베이스 작업을 간소화 하기 위해 데이터베이스 특성의 사용을 보여 줍니다.  
  
 데이터베이스에서 정보에 액세스 하는 기본적인 방법은 데이터베이스의 명령 (또는 테이블) 클래스 및 특정 테이블에 대 한 사용자 레코드 클래스를 만드는 것입니다. 데이터베이스 특성에는 일부 이전에 사용 했던 작업을 수행 하는 템플릿 선언을 단순화 합니다.  
  
 데이터베이스 특성의 사용을 보여 주기 위해 다음 섹션에서는 두 개의 동일한 테이블 및 사용자 레코드 클래스 선언이 보여: 특성을 사용 하는 첫 번째 및 두 번째 OLE DB 템플릿을 사용 합니다. 이러한 선언 코드는 일반적으로 authors.h 예를 들어 테이블이 나 명령 개체에 대 한 명명 된 헤더 파일에 들어 있습니다.  
  
 두 파일을 비교 하 여 특성을 사용 하는 방법을 보다 간단 하 게 볼 수 있습니다. 차이점 중:  
  
-   특성을 사용 해야 할 하나의 클래스를 선언: `CAuthors`템플릿으로 두 개를 선언 해야 하는 반면,: `CAuthorsNoAttrAccessor` 및 `CAuthorsNoAttr`합니다.  
  
-   `db_source` 특성이 지정 된 버전에서 호출 하는 것은 `OpenDataSource()` 템플릿 선언에서 호출 합니다.  
  
-   **db_table** 특성이 지정 된 버전에서 호출은 다음 템플릿 선언과 같습니다.  
  
    ```  
    class CAuthorsNoAttr : public CTable<CAccessor<CAuthorsNoAttrAccessor>>  
    ```  
  
-   **db_column** 호출 특성 사용된 하는 버전에서 열 지도 같습니다 (참조 `BEGIN_COLUMN_MAP ... END_COLUMN_MAP`) 템플릿 선언에 있습니다.  
  
 사용자에 대 한 사용자 레코드 클래스 선언을 삽입 합니다. 사용자 레코드 클래스에 해당 하는 `CAuthorsNoAttrAccessor` 템플릿 선언에 있습니다. 테이블 클래스 경우 `CAuthors`, 삽입 된 사용자 레코드 클래스의 이름은 `CAuthorsAccessor`, 해당 선언이 삽입 된 코드에만 볼 수 있습니다. 자세한 내용은 "특성 삽입 사용자 레코드 클래스"를 참조 [사용자 레코드](../../data/oledb/user-records.md)합니다.  
  
 특성 사용와 템플릿 기반 코드에서 사용 하 여 행 집합 속성 설정 해야 합니다 `CDBPropSet::AddProperty`합니다.  
  
 이 항목에서 설명 하는 특성에 대 한 정보를 참조 하십시오. [OLE DB 소비자 특성](../../windows/ole-db-consumer-attributes.md)합니다.  
  
## <a name="table-and-accessor-declaration-using-attributes"></a>테이블 및 특성을 사용 하는 접근자 선언  
 다음 호출 코드 `db_source` 및 **db_table** 테이블 클래스에 있습니다. `db_source` 데이터 원본 및 연결을 사용할 수를 지정 합니다. **db_table** 테이블 클래스 선언에 대 한 적절 한 템플릿 코드를 삽입 합니다. **db_column** 열 지도 지정 하 고 접근자 선언에 삽입 합니다. Atl이 지원 하는 프로젝트에서 OLE DB 소비자 특성을 사용할 수 있습니다.  
  
 테이블 및 접근자 선언 특성을 사용 하는 다음과 같습니다.  
  
```cpp
//////////////////////////////////////////////////////////////////////  
// Table and accessor declaration using attributes  
// authors.h  
//////////////////////////////////////////////////////////////////////  
  
// Table class declaration  
// (Note that you must provide your own connection string for db_source.)  
[  
   db_source(L"your connection string"),  
   db_table("Authors")  
]  
class CAuthors  
{  
public:  
   DWORD m_dwAuIDStatus;  
   DWORD m_dwAuthorStatus;  
   DWORD m_dwYearBornStatus;  
   DWORD m_dwAuIDLength;  
   DWORD m_dwAuthorLength;  
   DWORD m_dwYearBornLength;  
   [ db_column(1, status=m_dwAuIDStatus, length=m_dwAuIDLength) ] LONG m_AuID;  
   [ db_column(2, status=m_dwAuthorStatus, length=m_dwAuthorLength) ] TCHAR m_Author[51];  
   [ db_column(3, status=m_dwYearBornStatus, length=m_dwYearBornLength) ] SHORT m_YearBorn;  
   void GetRowsetProperties(CDBPropSet* pPropSet)  
   {  
      pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true);  
      pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true);  
      pPropSet->AddProperty(DBPROP_IRowsetChange, true);  
   }  
};  
```  
  
## <a name="table-and-accessor-declaration-using-templates"></a>테이블 및 템플릿을 사용 하 여 접근자 선언  
 템플릿을 사용 하 여 테이블 및 접근자 선언에는 다음과 같습니다.  
  
```cpp
//////////////////////////////////////////////////////////////////////  
// Table and user record class declaration using templates  
// authors.h  
//////////////////////////////////////////////////////////////////////  
  
// User record class declaration  
class CAuthorsNoAttrAccessor  
{  
public:  
   DWORD m_dwAuIDStatus;  
   DWORD m_dwAuthorStatus;  
   DWORD m_dwYearBornStatus;  
   DWORD m_dwAuIDLength;  
   DWORD m_dwAuthorLength;  
   DWORD m_dwYearBornLength;  
   LONG m_AuID;  
   TCHAR m_Author[51];  
   SHORT m_YearBorn;  
   void GetRowsetProperties(CDBPropSet* pPropSet)  
   {  
      pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true);  
      pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true);  
      pPropSet->AddProperty(DBPROP_IRowsetChange, true);  
   }  
   HRESULT OpenDataSource()  
   {  
      CDataSource _db;  

HRESULT hr;  
      hr = _db.OpenFromInitializationString(L"your connection string");  
      if (FAILED(hr))  
      {  
#ifdef _DEBUG  
         AtlTraceErrorRecords(hr);  
#endif  
         return hr;  
      }  
      return m_session.Open(_db);  
   }  
   void CloseDataSource()  
   {  
      m_session.Close();  
   }  
   operator const CSession&()  
   {  
      return m_session;  
   }  
   CSession m_session;  
   BEGIN_COLUMN_MAP(CAuthorsNoAttrAccessor)  
      COLUMN_ENTRY_LENGTH_STATUS(1, m_AuID, m_dwAuIDLength, m_dwAuIDStatus)  
      COLUMN_ENTRY_LENGTH_STATUS(2, m_Author, m_dwAuthorLength, m_dwAuthorStatus)  
      COLUMN_ENTRY_LENGTH_STATUS(3, m_YearBorn, m_dwYearBornLength, m_dwYearBornStatus)  
   END_COLUMN_MAP()  
};  
class CAuthorsNoAttr : public CTable<CAccessor<CAuthorsNoAttrAccessor>>  
{  
public:  
   HRESULT OpenAll()  
   {  
HRESULT hr;  
      hr = OpenDataSource();  
      if (FAILED(hr))  
         return hr;  
      __if_exists(GetRowsetProperties)  
      {  
         CDBPropSet propset(DBPROPSET_ROWSET);  
         __if_exists(HasBookmark)  
         {  
            propset.AddProperty(DBPROP_IRowsetLocate, true);  
         }  
         GetRowsetProperties(&propset);  
         return OpenRowset(&propset);  
      }  
      __if_not_exists(GetRowsetProperties)  
      {  
         __if_exists(HasBookmark)  
         {  
            CDBPropSet propset(DBPROPSET_ROWSET);  
            propset.AddProperty(DBPROP_IRowsetLocate, true);  
            return OpenRowset(&propset);  
         }  
      }  
      return OpenRowset();  
   }  
   HRESULT OpenRowset(DBPROPSET *pPropSet = NULL)  
   {  
HRESULT hr = Open(m_session, "Authors", pPropSet);  
#ifdef _DEBUG  
      if(FAILED(hr))  
         AtlTraceErrorRecords(hr);  
#endif  
      return hr;  
   }  
   void CloseAll()  
   {  
      Close();  
      CloseDataSource();  
   }  
};  
```  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 소비자 특성](../../windows/ole-db-consumer-attributes.md)   
 [특성 연습](http://msdn.microsoft.com/en-us/73df1d5d-261a-4521-98fb-06dcbf5ec0d0)