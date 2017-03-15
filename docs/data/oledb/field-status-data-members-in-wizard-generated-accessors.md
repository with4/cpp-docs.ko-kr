---
title: "마법사 생성 접근자의 필드 상태 데이터 멤버 | Microsoft Docs"
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
  - "OLE DB 템플릿의 필드 상태"
  - "OLE DB 소비자 템플릿, 필드 상태"
ms.assetid: 66e4e223-c60c-471e-860d-d23abcdfe371
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# 마법사 생성 접근자의 필드 상태 데이터 멤버
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ATL OLE DB 소비자 마법사를 사용하여 소비자를 만드는 경우, 마법사는 열 맵에서 지정한 각 필드에 대한 데이터 멤버를 사용자 레코드 클래스에 생성합니다.  각각의 데이터 멤버는 `DWORD` 형식이며 각자의 필드에 해당하는 상태 값이 들어 있습니다.  
  
 예를 들어, 데이터 멤버 *m\_OwnerID*의 경우 마법사는 필드 상태\(*dwOwnerIDStatus*\)에 대한 추가 데이터 멤버를 생성하고 필드 길이\(*dwOwnerIDLength*\)에 대한 다른 추가 데이터 멤버도 생성합니다.  또한 `COLUMN_ENTRY_LENGTH_STATUS` 엔트리가 포함된 열 맵도 생성합니다.  
  
 이는 다음 코드에서는 볼 수 있습니다.  
  
```  
[db_source("insert connection string")]  
[db_command(" \  
   SELECT \  
      Au_ID, \  
      Author, \  
      `Year Born`, \  
      FROM Authors")]  
  
class CAuthors  
{  
public:  
  
   // The following wizard-generated data members contain status   
   // values for the corresponding fields in the column map. You   
   // can use these values to hold NULL values that the database   
   // returns or to hold error information when the compiler returns   
   // errors. See "Field Status Data Members in Wizard-Generated   
   // Accessors" in the Visual C++ documentation for more information   
   // on using these fields.  
   DWORD m_dwAuIDStatus;  
   DWORD m_dwAuthorStatus;  
   DWORD m_dwYearBornStatus;  
  
   // The following wizard-generated data members contain length  
   // values for the corresponding fields in the column map.  
   DWORD m_dwAuIDLength;  
   DWORD m_dwAuthorLength;  
   DWORD m_dwYearBornLength;  
  
BEGIN_COLUMN_MAP(CAuthorsAccessor)  
   COLUMN_ENTRY_LENGTH_STATUS(1, m_AuID, dwAuIDLength, dwAuIDStatus)  
   COLUMN_ENTRY_LENGTH_STATUS(2, m_Author, dwAuthorLength, dwAuthorStatus)  
   COLUMN_ENTRY_LENGTH_STATUS(3, m_YearBorn, dwYearBornLength, dwYearBornStatus)  
END_COLUMN_MAP()  
  
   [ db_column(1, status=m_dwAuIDStatus, length=m_dwAuIDLength) ] LONG m_AuID;  
   [ db_column(2, status=m_dwAuthorStatus, length=m_dwAuthorLength) ] TCHAR m_Author[51];  
   [ db_column(3, status=m_dwYearBornStatus, length=m_dwYearBornLength) ] SHORT m_YearBorn;  
  
   void GetRowsetProperties(CDBPropSet* pPropSet)  
   {  
      pPropSet->AddProperty(DBPROP_IRowsetChange, true);  
      pPropSet->AddProperty(DBPROP_UPDATABILITY, DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_INSERT | DBPROPVAL_UP_DELETE);  
   }  
};  
```  
  
> [!NOTE]
>  사용자 레코드 클래스를 수정하거나 사용자 고유의 소비자를 작성하는 경우, 데이터 변수가 상태 변수와 길이 변수보다 앞에 있어야 합니다.  
  
 디버깅을 위해 상태 값을 사용할 수 있습니다.  ATL OLE DB 소비자 마법사에서 생성한 코드가 **DB\_S\_ERRORSOCCURRED**나 **DB\_E\_ERRORSOCCURRED** 같은 컴파일 오류를 생성하는 경우, 먼저 필드 상태 데이터 멤버의 현재 값을 살펴봐야 합니다.  현재 값이 0이 아니면 오류를 생성하는 열에 해당합니다.  
  
 사용자는 또한 상태 값을 사용하여 특정 필드에 대해 NULL 값을 설정할 수도 있습니다.  이렇게 하면 필드 값을 0이 아닌 NULL 값으로 구분하고자 하는 경우에 도움이 됩니다.  NULL이 유효한 값인지 아니면 특수 값인지의 여부 및 응용 프로그램이 이 값을 처리하는 방법을 결정하는 것은 사용자의 몫입니다.  OLE DB는 **DBSTATUS\_S\_ISNULL**을 일반 NULL 값으로 지정하는 올바른 방법으로서 정의합니다.  소비자가 읽은 데이터의 값이 null인 경우, 상태 필드는 **DBSTATUS\_S\_ISNULL**로 설정됩니다.  소비자가 NULL 값을 설정하려는 경우, 소비자는 공급자를 호출하기 전에 상태 값을 **DBSTATUS\_S\_ISNULL**로 설정합니다.  
  
 그런 다음 Oledb.h를 열고 **DBSTATUSENUM**을 검색합니다.  **DBSTATUSENUM** 열거형 값을 기준으로 0이 아닌 상태의 숫자 값을 일치시킬 수 있습니다.  If the enumeration name is not sufficient to tell you what is wrong, see the "Status" topic in the "Binding Data Values" section of the [OLE DB Programmer's Guide](http://go.microsoft.com/fwlink/?LinkId=121548).  이 항목에는 데이터를 가져오거나 설정할 때 사용되는 상태 값의 표가 들어 있습니다.  길이 값에 대한 자세한 내용은 같은 단원의 "Length" 항목을 참조하십시오.  
  
## 열의 길이 또는 상태 검색  
 예를 들어 **DBSTATUS\_S\_ISNULL**을 확인하기 위해, 가변 길이 열의 길이나 열의 상태를 검색할 수 있습니다.  
  
-   길이를 구하려면 `COLUMN_ENTRY_LENGTH` 매크로를 사용합니다.  
  
-   상태를 구하려면 `COLUMN_ENTRY_STATUS` 매크로를 사용합니다.  
  
-   두 가지 모두를 구하려면 아래 예제에서처럼 `COLUMN_ENTRY_LENGTH_STATUS`를 사용합니다.  
  
```  
class CProducts  
{  
public:  
   char      szName[40];  
   long      nNameLength;  
   DBSTATUS   nNameStatus;  
  
BEGIN_COLUMN_MAP(CProducts)  
// Bind the column to CProducts.m_ProductName.  
// nOrdinal is zero-based, so the column number of m_ProductName is 1.  
   COLUMN_ENTRY_LENGTH_STATUS(1, szName, nNameLength, nNameStatus)  
END_COLUMN_MAP()  
};  
  
CTable<CAccessor<CProducts > > product;  
  
product.Open(session, "Product");  
while (product.MoveNext() == S_OK)  
{  
   // Check the product name isn't NULL before tracing it  
   if (product.nNameStatus == DBSTATUS_S_OK)  
      ATLTRACE("%s is %d characters\n", szName, nNameLength);  
}  
```  
  
 `CDynamicAccessor`를 사용할 때 길이와 상태는 사용자에 대해 자동으로 바인딩됩니다.  길이와 상태 값을 검색하려면 `GetLength` 및 **GetStatus** 멤버 함수를 사용하십시오.  
  
## 참고 항목  
 [OLE DB 소비자 템플릿 작업](../../data/oledb/working-with-ole-db-consumer-templates.md)