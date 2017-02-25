---
title: "레코드 집합: 레코드 집합의 레코드 선택 방법(ODBC) | Microsoft Docs"
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
  - "ODBC 레코드 집합, 레코드 선택"
  - "레코드 선택, ODBC 레코드 집합"
  - "레코드, 선택"
  - "레코드 집합, SQL 문 구성"
  - "레코드 집합, 레코드 선택"
  - "SQL 문, 레코드 집합"
ms.assetid: 343a6a91-aa4c-4ef7-b21f-2f2bfd0d3787
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# 레코드 집합: 레코드 집합의 레코드 선택 방법(ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목은 MFC ODBC 클래스에 적용됩니다.  
  
 다음은 이 항목에서 설명하는 내용입니다.  
  
-   [레코드를 선택할 때의 역할과 옵션](#_core_your_options_in_selecting_records).  
  
-   [레코드 집합이 SQL 문을 생성하는 방법과 레코드를 선택하는 방법](#_core_how_a_recordset_constructs_its_sql_statement).  
  
-   [선택 사용자 지정을 위한 작업](#_core_customizing_the_selection).  
  
 레코드 집합은 드라이버를 통해 데이터 소스에서 레코드를 선택하며, 이 경우 SQL 문을 ODBC 드라이버에 보내는 방법을 사용합니다.  보내지는 SQL 문은 레코드 집합 클래스를 디자인하고 여는 방법에 따라 다릅니다.  
  
##  <a name="_core_your_options_in_selecting_records"></a> 레코드 선택의 옵션  
 다음 표에는 레코드 선택 시 사용할 수 있는 옵션이 나와 있습니다.  
  
### 레코드 집합에 영향을 주는 방법과 시기  
  
|시기|옵션|  
|--------|--------|  
|**클래스 추가** 마법사로 레코드 집합 클래스를 선언할 때|선택할 테이블을 지정합니다.<br /><br /> 포함할 열을 지정합니다.<br /><br /> [MFC ODBC 소비자 추가](../../mfc/reference/adding-an-mfc-odbc-consumer.md)를 참조하십시오.|  
|레코드 집합 클래스 구현을 완료할 때|`OnSetOptions`\(고급\) 같은 멤버 함수를 재정의하여 응용 프로그램 고유의 옵션을 설정하거나 기본값을 변경합니다.  매개 변수가 있는 레코드 집합을 만들려면 매개 변수 데이터 멤버를 지정합니다.|  
|**Open**을 호출하기 전에 레코드 집합 개체를 생성합니다.|레코드를 필터링하는 **WHERE** 절에 사용할 검색 조건\(복합 조건도 가능\)을 지정합니다.  [레코드 집합: 레코드 필터링\(ODBC\)](../../data/odbc/recordset-filtering-records-odbc.md)을 참조하십시오.<br /><br /> 레코드를 정렬하는 **ORDER BY** 절에 사용할 정렬 순서를 지정합니다.  [레코드 집합: 레코드 정렬\(ODBC\)](../../data/odbc/recordset-sorting-records-odbc.md)을 참조하십시오.<br /><br /> 클래스에 추가한 매개 변수에 대해 매개 변수 값을 지정합니다.  [레코드 집합: 레코드 집합 매개 변수화\(ODBC\)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)를 참조하십시오.|  
|**Open**을 호출하여 레코드 집합의 쿼리를 실행할 때|사용자 지정 SQL 문자열을 지정하여 마법사에서 설정한 기본 SQL 문자열을 바꿉니다.  [SQL: 레코드 집합의 SQL 문 사용자 지정\(ODBC\)](../../data/odbc/sql-customizing-your-recordset’s-sql-statement-odbc.md) 및 클래스 라이브러리 참조의 [CRecordset::Open](../Topic/CRecordset::Open.md)를 참조하십시오.|  
|데이터 소스의 최신 값으로 레코드 집합을 다시 쿼리하기 위해 **Requery**를 호출할 때|새 매개 변수, 필터 또는 정렬을 지정합니다.  [레코드 집합: 레코드 집합 다시 쿼리\(ODBC\)](../../data/odbc/recordset-requerying-a-recordset-odbc.md)를 참조하십시오.|  
  
##  <a name="_core_how_a_recordset_constructs_its_sql_statement"></a> 레코드 집합의 SQL 문 생성 방법  
 레코드 집합 개체의 [Open](../Topic/CRecordset::Open.md) 멤버 함수를 호출하면 **Open**은 다음 요소 중 일부 또는 전부를 사용하여 SQL 문을 생성합니다.  
  
-   **Open**에 전달된 **lpszSQL** 매개 변수.  이 매개 변수가 **NULL**이 아니면 사용자 지정 SQL 문자열 또는 그 일부가 지정되며  프레임워크에서는 문자열을 구문 분석합니다.  문자열이 SQL **SELECT** 문이거나 ODBC **CALL** 문이면 프레임워크는 문자열을 레코드 집합의 SQL 문으로 사용합니다.  문자열이 "SELECT" 또는 "{CALL"로 시작되지 않으면 프레임워크에서는 제공된 문자열을 사용하여 SQL **FROM** 절을 만듭니다.  
  
-   [GetDefaultSQL](../Topic/CRecordset::GetDefaultSQL.md)에서 반환된 문자열.  기본적으로 이 문자열은 마법사에서 레코드 집합에 대해 지정한 테이블 이름이지만 함수에서 반환하는 문자열을 변경할 수도 있습니다.  프레임워크에서는 `GetDefaultSQL`을 호출합니다. 문자열이 "SELECT" 또는 "{CALL"로 시작되지 않으면 테이블 이름으로 간주하여 SQL 문자열 생성에 사용됩니다.  
  
-   레코드 집합의 필드 데이터 멤버. 이것은 테이블의 특정 열에 바인딩됩니다.  프레임워크에서는 레코드 열을 이 멤버의 주소에 바인딩하고 이 멤버를 버퍼로 사용합니다.  프레임워크는 레코드 집합의 [DoFieldExchange](../Topic/CRecordset::DoFieldExchange.md) 또는 [DoBulkFieldExchange](../Topic/CRecordset::DoBulkFieldExchange.md) 멤버 함수에서 [RFX](../../data/odbc/record-field-exchange-using-rfx.md) 또는 대량 RFX 함수를 호출하여 필드 데이터 멤버와 테이블 열의 상관 관계를 결정합니다.  
  
-   [m\_strFilter](../Topic/CRecordset::m_strFilter.md) 데이터 멤버에 포함된 레코드 집합의 [필터](../../data/odbc/recordset-filtering-records-odbc.md)\(있을 경우\).  프레임워크에서는 이 문자열을 사용하여 SQL **WHERE** 절을 생성합니다.  
  
-   [m\_strSort](../Topic/CRecordset::m_strSort.md) 데이터 멤버에 포함된 레코드 집합의 [정렬](../../data/odbc/recordset-sorting-records-odbc.md) 순서.  프레임워크에서는 이 문자열을 사용하여 SQL **ORDER BY** 절을 생성합니다.  
  
    > [!TIP]
    >  SQL **GROUP BY** 절 및 **HAVING** 절은 필터 문자열의 끝에 추가합니다.  
  
-   클래스에 지정하는 모든 [매개 변수 데이터 멤버](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)의 값.  **Open** 또는 **Requery**를 호출하기 직전에 매개 변수 값을 설정합니다.  프레임워크에서는 SQL 문자열의 "?" 자리 표시자에 매개 변수 값을 바인딩합니다.  컴파일 타임에 자리 표시자를 사용하여 문자열을 지정합니다.  런타임에 프레임워크는 사용자가 전달하는 매개 변수 값에 기반하여 세부 사항을 지정합니다.  
  
 **Open**은 위의 요소를 사용하여 SQL **SELECT** 문을 생성합니다.  프레임워크가 이 요소들을 사용하는 방법에 대한 자세한 내용은 [선택 사용자 지정](#_core_customizing_the_selection) 문서를 참조하십시오.  
  
 SQL 문을 생성한 다음 **Open**은 SQL을 ODBC 드라이버 관리자 및 ODBC 커서 라이브러리\(메모리에 있을 경우\)에 보내고 ODBC 드라이버 관리자는 이를 특정 DBMS의 ODBC 드라이버에 보냅니다.  드라이버는 DBMS와 통신하여 데이터 소스에서 레코드를 선택하여 이 중 첫째 레코드를 페치합니다.  프레임워크에서는 이 레코드를 레코드 집합의 필드 데이터 멤버에 로드합니다.  
  
 이러한 기술을 함께 사용하여 [테이블](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)을 열고 여러 테이블의 [조인](../../data/odbc/recordset-performing-a-join-odbc.md)을 기반으로 하는 쿼리를 생성할 수 있습니다.  또한 다른 사항을 추가적으로 사용자 지정하여 [미리 정의된 쿼리](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)\(저장 프로시저\)를 호출하고, 디자인 타임에는 알 수 없는 테이블 열을 선택하여 레코드 집합 필드에 [바인딩](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)하거나 대부분의 다른 데이터에 액세스할 수 있습니다.  레코드 집합을 사용자 지정하여 수행할 수 없는 작업은 [ODBC API 함수를 호출](../../data/odbc/odbc-calling-odbc-api-functions-directly.md)하여 수행하거나 [CDatabase::ExecuteSQL](../Topic/CDatabase::ExecuteSQL.md)을 사용하여 직접 SQL 문을 실행하여 수행합니다.  
  
##  <a name="_core_customizing_the_selection"></a> 선택 사용자 지정  
 필터, 정렬 순서 또는 매개 변수를 제공하는 것 외에도 다음과 같은 작업을 통해 레코드 집합의 선택을 사용자 지정할 수 있습니다.  
  
-   레코드 집합에 대해 [Open](../Topic/CRecordset::Open.md)을 호출할 때 **lpszSQL**에 사용자 지정 SQL 문자열을 전달합니다.  **lpsqSQL**에 전달되는 문자열이 [GetDefaultSQL](../Topic/CRecordset::GetDefaultSQL.md) 멤버 함수에서 반환되는 것보다 우선합니다.  
  
     자세한 내용은 **Open**에 전달할 수 있는 SQL 문\(또는 부분 문\)의 종류와 이를 사용하여 프레임워크에서 수행하는 작업에 대해 설명하는 [SQL: 레코드 집합의 SQL 문 사용자 지정\(ODBC\)](../../data/odbc/sql-customizing-your-recordset’s-sql-statement-odbc.md)을 참조하십시오.  
  
    > [!NOTE]
    >  전달되는 사용자 지정 문자열이 "SELECT" 또는 "{CALL"로 시작되지 않으면 MFC는 이 문자열에 테이블 이름이 포함된 것으로 간주합니다.  이 참고 내용은 글머리 기호 항목에도 적용됩니다.  
  
-   마법사에서 레코드 집합의 `GetDefaultSQL` 멤버 함수에 작성한 문자열을 바꿉니다.  함수 코드를 편집하여 함수의 반환 값을 변경하십시오.  기본적으로 마법사에서는 단일 테이블 이름을 반환하는 `GetDefaultSQL` 함수를 작성합니다.  
  
     `GetDefaultSQL` 함수를 수정하여 **lpszSQL** 매개 변수를 사용하여 **Open** 함수에 특정 항목을 전달할 수 있도록 할 수 있습니다.  사용자 지정 SQL 문자열을 **lpszSQL**에 전달하지 않으면 프레임워크는 `GetDefaultSQL`이 반환하는 문자열을 사용합니다.  `GetDefaultSQL`은 최소한 단일 테이블 이름을 반환해야 하지만  여러 개의 테이블 이름, 전체 **SELECT** 문, ODBC **CALL** 문 등을 반환하도록 수정할 수 있습니다.  `GetDefaultSQL`이 반환하거나, **lpszSQL**에 전달할 수 있는 매개 변수 목록에 대해서는 [SQL: 레코드 집합의 SQL 문 사용자 지정\(ODBC\)](../../data/odbc/sql-customizing-your-recordset’s-sql-statement-odbc.md)을 참조하십시오.  
  
     둘 이상의 테이블을 조인하는 경우 `GetDefaultSQL`을 다시 작성하여 SQL **FROM** 절에 사용되는 테이블 목록을 사용자 지정합니다.  자세한 내용은 [레코드 집합: 조인 수행\(ODBC\)](../../data/odbc/recordset-performing-a-join-odbc.md)을 참조하십시오.  
  
-   런타임에 얻은 데이터 소스의 스키마에 대한 정보 등을 기반으로 추가 필드 데이터 멤버를 사용자가 직접 바인딩합니다.  레코드 집합 클래스에 필드 데이터 멤버를 추가하고, 이러한 데이터 멤버를 위한 [RFX](../../data/odbc/record-field-exchange-using-rfx.md) 또는 대량 RFX 함수 호출을 [DoFieldExchange](../Topic/CRecordset::DoFieldExchange.md)나 [DoBulkFieldExchange](../Topic/CRecordset::DoBulkFieldExchange.md) 멤버 함수에 추가하고, 클래스 생성자에서 데이터 멤버를 초기화합니다.  자세한 내용은 [레코드 집합: 데이터 열 동적 바인딩\(ODBC\)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)을 참조하십시오.  
  
-   `OnSetOptions` 같은 레코드 집합 멤버 함수를 재정의하여 응용 프로그램 고유의 옵션을 설정하거나 기본값을 재정의합니다.  
  
 복합 SQL 문을 기반으로 레코드 집합을 만들려면 이러한 사용자 지정 기술을 함께 사용해야 합니다.  그러한 예로 레코드 집합에서 직접 지원되지 않는 SQL 절과 키워드를 사용하거나 여러 테이블을 조인해야 하는 경우가 있습니다.  
  
## 참고 항목  
 [레코드 집합\(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [레코드 집합: 레코드 집합의 레코드 업데이트 방법\(ODBC\)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)   
 [ODBC 기초](../../data/odbc/odbc-basics.md)   
 [SQL](../../data/odbc/sql.md)   
 [레코드 집합: 레코드 잠금\(ODBC\)](../../data/odbc/recordset-locking-records-odbc.md)