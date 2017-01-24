---
title: "데이터베이스 특성을 사용하여 데이터 액세스 단순화 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-attr.db_param"
  - "vc-attr.db_column"
  - "vc-attr.db_accessor"
  - "vc-attr.db_command"
  - "vc-attr.db_table"
  - "vc-attr.db_source"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "특성[C++], 데이터 액세스"
  - "특성[C++], 데이터베이스"
  - "특성[C++], OLE DB 소비자"
  - "데이터[C++], 액세스 단순화"
  - "데이터 액세스[C++], 데이터베이스 특성"
  - "데이터베이스 특성[C++]"
  - "데이터베이스[C++], 특성"
  - "OLE DB 소비자[C++], 데이터베이스 특성"
ms.assetid: 560d2456-e307-4cb7-ba7b-4d0ed674697f
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 데이터베이스 특성을 사용하여 데이터 액세스 단순화
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

여기에서는 데이터베이스 작업을 단순화하기 위한 데이터베이스 특성 사용에 대해 설명합니다.  
  
 데이터베이스의 정보에 액세스하는 기본 방식은 데이터베이스의 특정 테이블에 대해 명령\(또는 테이블\) 클래스와 사용자 레코드 클래스를 만드는 것입니다.  데이터베이스 특성을 사용하면 이전에 사용자가 수행해야 했던 일부 템플릿 선언을 단순화할 수 있습니다.  
  
 데이터베이스 특성의 사용을 설명하기 위해 다음 섹션에는 대응되는 두 개의 테이블 및 사용자 레코드 클래스 선언이 나옵니다. 첫 번째 섹션에서는 특성을 사용하고 두 번째 섹션에서는 OLE DB 템플릿을 사용합니다.  이러한 선언 코드는 일반적으로 Authors.h처럼 테이블이나 명령 개체의 이름으로 지정된 헤더 파일에 들어 있습니다.  
  
 두 파일을 비교하면 특성을 사용하는 것이 얼마나 간단한 방법인지 알 수 있습니다.  다음은 두 파일의 차이점입니다.  
  
-   특성을 사용하는 경우에는 하나의 클래스 `CAuthors`만 선언하면 되지만, 템플릿을 사용하는 경우에는 두 개의 클래스 `CAuthorsNoAttrAccessor`와 `CAuthorsNoAttr`를 선언해야 합니다.  
  
-   특성 사용 버전에서의 `db_source` 호출은 템플릿 선언에서의 `OpenDataSource()` 호출에 해당합니다.  
  
-   특성 사용 버전에서의 **db\_table** 호출은 다음 템플릿 선언에 해당합니다.  
  
    ```  
    class CAuthorsNoAttr : public CTable<CAccessor<CAuthorsNoAttrAccessor> >  
    ```  
  
-   특성 사용 버전에서의 **db\_column** 호출은 템플릿 선언에서의 열 맵\(`BEGIN_COLUMN_MAP ... END_COLUMN_MAP` 참조\)에 해당합니다.  
  
 특성은 사용자 레코드 클래스 선언을 삽입합니다.  사용자 레코드 클래스는 템플릿 선언에서의 `CAuthorsNoAttrAccessor`에 해당합니다.  테이블 클래스가 `CAuthors`인 경우 삽입된 사용자 레코드 클래스의 이름은 `CAuthorsAccessor`가 되며 삽입된 코드에서만 선언을 볼 수 있습니다.  자세한 내용은 [사용자 레코드](../../data/oledb/user-records.md)의 "특성 삽입 사용자 레코드 클래스"를 참조하십시오.  
  
 특성 사용 코드 및 템플릿 기반 코드 모두에서 `CDBPropSet::AddProperty`를 사용하여 행 집합 속성을 설정해야 한다는 점에 주의하십시오.  
  
 여기에 나온 특성에 대한 자세한 내용은 [OLE DB 소비자 특성](../../windows/ole-db-consumer-attributes.md)을 참조하십시오.  
  
## 특성을 사용한 테이블 및 접근자 선언  
 다음 코드에서는 테이블 클래스에서 `db_source`와 **db\_table**을 호출합니다.  `db_source`는 사용될 데이터 소스와 연결을 지정하고  **db\_table**은 테이블 클래스를 선언하는 데 알맞은 템플릿 코드를 삽입합니다.  **db\_column**은 열 맵을 지정하고 접근자 선언을 삽입합니다.  ATL을 지원하는 모든 프로젝트에서 OLE DB 소비자 특성을 사용할 수 있습니다.  
  
 다음은 특성을 사용한 테이블 및 접근자 선언입니다.  
  
```  
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
  
## 템플릿을 사용한 테이블 및 접근자 선언  
 다음은 템플릿을 사용한 테이블 및 접근자 선언입니다.  
  
```  
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
class CAuthorsNoAttr : public CTable<CAccessor<CAuthorsNoAttrAccessor> >  
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
  
## 참고 항목  
 [OLE DB Consumer Attributes](../../windows/ole-db-consumer-attributes.md)   
 [Attributes Walkthroughs](http://msdn.microsoft.com/ko-kr/73df1d5d-261a-4521-98fb-06dcbf5ec0d0)