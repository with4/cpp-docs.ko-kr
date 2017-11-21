---
title: "마법사 생성 접근자의 상태 데이터 멤버 필드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE DB consumer templates, field status
- field status in OLE DB templates
ms.assetid: 66e4e223-c60c-471e-860d-d23abcdfe371
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e3991e2e5cab8814cba4e92882fbd978bdc051eb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="field-status-data-members-in-wizard-generated-accessors"></a>마법사 생성 접근자의 필드 상태 데이터 멤버
ATL OLE DB 소비자 마법사를 사용 하 여 소비자를 만드는 마법사를 열 지도에 지정 하는 각 필드에 대 한 사용자 레코드 클래스에에서 데이터 멤버를 생성 합니다. 각 데이터 멤버는 형식의 `DWORD` 각 필드에 해당 하는 상태 값을 포함 합니다.  
  
 데이터 멤버에 대 한 예를 들어 *m_OwnerID*, 필드의 상태에 대 한 추가 데이터 멤버를 생성 하는 마법사 (*dwOwnerIDStatus*) 및 필드 길이 대 한 다른 하나 (*dwOwnerIDLength*). 또한 포함 된 열 맵 생성 `COLUMN_ENTRY_LENGTH_STATUS` 항목입니다.  
  
 이 다음 코드에 나와 있습니다.  
  
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
>  사용자 레코드 클래스를 수정하거나 사용자 고유의 소비자를 작성하는 경우 데이터 변수가 상태 및 길이 변수 앞에 와야 합니다.  
  
 디버깅 목적으로 상태 값을 사용할 수 있습니다. ATL OLE DB 소비자 마법사에서 생성 된 코드와 같은 컴파일 오류를 생성 하는 경우 **DB_S_ERRORSOCCURRED** 또는 **DB_E_ERRORSOCCURRED**, 먼저 살펴봐야 필드 상태의 현재 값 데이터 멤버입니다. 0이 아닌 값이 있는 생성 하는 열에 해당 합니다.  
  
 또한 특정 필드에 NULL 값을 설정 하는 상태 값을 사용할 수 있습니다. 이렇게 하면 0이 아닌 NULL로 필드 값을 구분 하기 위해 원하는 경우에 도움이 됩니다. 사용자가 결정 하는 특수 값 또는 유효한 값을 NULL 인지 여부를 결정 하 고 응용 프로그램 해야 처리 하는 방법을 결정 합니다. OLE DB 정의 **DBSTATUS_S_ISNULL** 제네릭 NULL 값을 지정 하는 올바른 방법으로 합니다. 상태 필드 설정 되어 소비자가 데이터를 읽는 경우 값이 null **DBSTATUS_S_ISNULL**합니다. 소비자 상태 값을 설정 하는 소비자를 NULL 값을 설정 하려는 경우 **DBSTATUS_S_ISNULL** 공급자를 호출 하기 전에.  
  
 다음으로, Oledb.h를 열고 검색 **DBSTATUSENUM**합니다. 0이 아닌 상태에 대 한 숫자 값을 일치 시킬 수 있습니다는 **DBSTATUSENUM** 열거형 값입니다. 열거형 이름으로 문제를 파악 하는 충분 하지 않을 경우의 "데이터 값 바인딩" 섹션에서 "상태" 항목을 참조 하십시오.는 [OLE DB Programmer's Guide](http://go.microsoft.com/fwlink/?linkid=121548)합니다. 이 항목의 상태 값을 가져오거나 데이터를 설정할 때 사용 되는 테이블을 포함 합니다. 길이 값에 대 한 내용은 동일한 섹션에서 "길이" 항목을 참조 합니다.  
  
## <a name="retrieving-the-length-or-status-of-a-column"></a>길이 또는 열의 상태를 검색합니다.  
 가변 길이 열의 길이 또는 열의 상태를 검색할 수 있습니다 (확인 **DBSTATUS_S_ISNULL**예):  
  
-   길이 가져오려면는 `COLUMN_ENTRY_LENGTH` 매크로입니다.  
  
-   상태를 가져오려면는 `COLUMN_ENTRY_STATUS` 매크로입니다.  
  
-   둘 다를 가져오려면 `COLUMN_ENTRY_LENGTH_STATUS`다음과 같이 합니다.  
  
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
  
 사용 하는 경우 `CDynamicAccessor`, 길이 및 상태에 바인딩되고 하면 자동으로 합니다. 길이 및 상태 값을 검색 하려면 사용 하 여는 `GetLength` 및 **GetStatus** 멤버 함수입니다.  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 소비자 템플릿 작업](../../data/oledb/working-with-ole-db-consumer-templates.md)