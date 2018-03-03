---
title: "레코드 집합: 레코드 집합 선택 레코드 방법 (ODBC) | Microsoft Docs"
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
- recordsets, selecting records
- record selection, ODBC recordsets
- SQL statements, recordset
- records, selecting
- recordsets, constructing SQL statements
- ODBC recordsets, selecting records
ms.assetid: 343a6a91-aa4c-4ef7-b21f-2f2bfd0d3787
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8664c5732c0cdf1042b6af338ea388ab29ab7863
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="recordset-how-recordsets-select-records-odbc"></a>레코드 집합: 레코드 집합의 레코드 선택 방법(ODBC)
MFC ODBC 클래스에이 항목에 적용 됩니다.  
  
 이 항목에 설명 합니다.  
  
-   [사용자의 역할 및 레코드를 선택 하면 다음에서 옵션](#_core_your_options_in_selecting_records)합니다.  
  
-   [레코드 집합 SQL 문을 생성 하 고 레코드를 선택 하는 방법을](#_core_how_a_recordset_constructs_its_sql_statement)합니다.  
  
-   [선택 사용자 지정을 수행할 수 있는](#_core_customizing_the_selection)합니다.  
  
 레코드 집합에서 드라이버에 SQL 문을 전송 하 여 ODBC 드라이버를 통해 데이터 원본에서 레코드를 선택 합니다. 전송 SQL 설계 하 고 레코드 집합 클래스를 열고 하는 방식에 따라 달라 집니다.  
  
##  <a name="_core_your_options_in_selecting_records"></a>레코드 선택의 옵션  
 다음 표에서 레코드를 선택 하 여 옵션을 보여 줍니다.  
  
### <a name="how-and-when-you-can-affect-a-recordset"></a>레코드 집합 나오는지 방식 및 시기  
  
|때 있습니다|다음과 같은 작업을 수행할 수 있습니다.|  
|--------------|-------------|  
|클래스를 선언할 때 레코드 집합으로는 **클래스 추가** 마법사|테이블에서 선택할 수를 지정 합니다.<br /><br /> 포함할 열을 지정 합니다.<br /><br /> 참조 [MFC ODBC 소비자 추가](../../mfc/reference/adding-an-mfc-odbc-consumer.md)합니다.|  
|레코드 집합 클래스 구현을 완료합니다|와 같은 멤버 함수를 재정의 `OnSetOptions` 응용 프로그램별 옵션을 설정 하거나 기본값을 변경 (고급). 매개 변수가 있는 레코드 집합을 원하는 경우에 매개 변수 데이터 멤버를 지정 합니다.|  
|레코드 집합 개체를 생성 합니다 (호출 하기 전에 **열려**)|사용 하기 위해 (복합 조건도 가능) 검색 조건을 지정는 **여기서** 레코드를 필터링 하는 절. 참조 [레코드 집합: 레코드 필터링 (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)합니다.<br /><br /> 사용 하기 위해 정렬 순서를 지정 된 **ORDER BY** 레코드를 정렬 하는 절. 참조 [레코드 집합: 레코드 정렬 (ODBC)](../../data/odbc/recordset-sorting-records-odbc.md)합니다.<br /><br /> 클래스에 추가 하는 모든 매개 변수에 대 한 매개 변수 값을 지정 합니다. 참조 [레코드 집합: 레코드 집합 (ODBC)를 매개 변수화](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)합니다.|  

| 호출 하 여 레코드 집합의 쿼리를 실행할 **열려**| 마법사에서 설정 하는 기본 SQL 문자열을 대체 하는 사용자 지정 SQL 문자열을 지정 합니다. 참조 [crecordset:: Open](../../mfc/reference/crecordset-class.md#open) 에 *클래스 라이브러리 참조* 및 [SQL: 레코드 집합의 SQL 문 (ODBC) 사용자 지정](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md). |  

| 호출 **Requery** 데이터 원본에서 최신 값으로 레코드 집합을 | 새 매개 변수, 필터 또는 정렬을 지정 합니다. 참조 [레코드 집합: 레코드 집합 (ODBC) 다시 쿼리](../../data/odbc/recordset-requerying-a-recordset-odbc.md). |  
  
##  <a name="_core_how_a_recordset_constructs_its_sql_statement"></a>레코드 집합의 SQL 문을 생성 하는 방법  
 레코드 집합 개체를 호출 하는 경우 [열려](../../mfc/reference/crecordset-class.md#open) 멤버 함수 **열려** 은 다음 요소의 일부나 전부를 사용 하 여 SQL 문을 생성:  
  
-   **lpszSQL** 전달 된 매개 변수가 **열려**합니다. 그렇지 않은 경우 **NULL**, 사용자 지정 SQL 문자열 또는 그 일부가이 매개 변수를 지정 합니다. 프레임 워크는 문자열을 구문 분석 합니다. 문자열이 SQL 인지 **선택** 문이나 ODBC **호출** 문, 프레임 워크 레코드 집합의 SQL 문으로 문자열을 사용 합니다. 문자열 "SELECT" 또는 "{CALL"로 시작 하지 않으므로, 공급 되는 SQL을 생성 하는 프레임 워크 사용 **FROM** 절.  
  
-   반환한 문자열 [GetDefaultSQL](../../mfc/reference/crecordset-class.md#getdefaultsql)합니다. 기본적으로이 마법사에서 레코드 집합에 대해 지정 된 테이블의 이름이 있지만 함수에서 반환 하는 대상을 변경할 수 있습니다. 프레임 워크를 호출 하 여 `GetDefaultSQL` -문자열 "SELECT" 또는 "{CALL"로 시작 하지 않으므로, SQL 문자열을 생성 하는 데 사용 되는 테이블 이름으로 간주 됩니다.  
  

-   필드 데이터 멤버는 레코드 집합의 테이블의 특정 열에 바인딩될 수 있습니다. 프레임 워크를 버퍼로 사용 이러한 멤버의 주소 레코드 열을 바인딩합니다. 테이블 열을 필드 데이터 멤버의 상관 관계를 확인 하는 프레임 워크는 [RFX](../../data/odbc/record-field-exchange-using-rfx.md) 레코드 집합의 대량 RFX 함수 호출 또는 [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) 또는 [DoBulkFieldExchange ](../../mfc/reference/crecordset-class.md#dofieldexchange) 멤버 함수입니다.  
  
-   [필터](../../data/odbc/recordset-filtering-records-odbc.md) 레코드 집합에 있는 경우에 포함 된는 [m_strFilter](../../mfc/reference/crecordset-class.md#m_strfilter) 데이터 멤버입니다. 프레임 워크에서이 문자열을 사용 하 여 한 SQL을 구성을 **여기서** 절.  
  
-   [정렬](../../data/odbc/recordset-sorting-records-odbc.md) 에 들어 있는 경우는 레코드 집합에 대 한 순서는 [m_strSort](../../mfc/reference/crecordset-class.md#m_strsort) 데이터 멤버입니다. 프레임 워크에서이 문자열을 사용 하 여 한 SQL을 구성을 **ORDER BY** 절.  

  
    > [!TIP]
    >  SQL을 사용 하려면 **GROUP BY** 절 (해야 했으며는 **HAVING** 절)을 필터 문자열의 끝에 절을 추가 합니다.  
  
-   값 [매개 변수 데이터 멤버](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) 클래스에 지정 합니다. 바로 전에 호출 하면 매개 변수 값을 설정한 **열려** 또는 **Requery**합니다. 프레임 워크 바인딩하여 매개 변수 값을 "?"에 SQL 문자열의 자리 표시자입니다. 컴파일 타임에 자리 표시자와 문자열을 지정 합니다. 런타임 시 프레임 워크를 전달 하면 매개 변수 값을 기반으로 하는 정보에 채웁니다.  
  
 **열기** SQL 생성 **선택** 이러한 구성 요소에서 문의 합니다. 참조 [선택 사용자 지정](#_core_customizing_the_selection) 프레임 워크는 요소를 사용 하는 방법에 대 한 세부 정보에 대 한 합니다.  
  
 문을 생성 한 후 **열려** SQL ODBC 드라이버 관리자 (및 ODBC 커서 라이브러리 메모리에 있는 경우)에 게 보냅니다는 보냅니다 ODBC 드라이버는 특정 DBMS에 대 한 합니다. 드라이버에서 데이터 원본 선택 항목을 수행 하는 DBMS와 통신 하 고 첫 번째 레코드를 인출 합니다. 프레임 워크는 레코드 집합의 필드 데이터 멤버에는 레코드를 로드합니다.  
  
 이러한 기술 함께 사용 하 여 열려는 [테이블](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md) 기반으로 쿼리를 작성 하 고는 [조인](../../data/odbc/recordset-performing-a-join-odbc.md) 여러 테이블. 추가 사용자 지정과 호출할 수 있습니다 [미리 정의 된 쿼리](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md) (저장된 프로시저)를 테이블 열을 선택 디자인 타임에 알 수 없는 및 [바인딩할](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md) 대부분의 다른 수행할 수 있습니다 또는 레코드 집합 필드 데이터 액세스 작업입니다. 레코드 집합을 사용자 지정 하 여 수행할 수 없는 작업을 하 여 수행할 수 여전히 [ODBC API 함수 호출](../../data/odbc/odbc-calling-odbc-api-functions-directly.md) 가 있는 SQL 문을 직접 실행 하거나 [CDatabase::ExecuteSQL](../../mfc/reference/cdatabase-class.md#executesql)합니다.  
  
##  <a name="_core_customizing_the_selection"></a>선택 사용자 지정  
 필터, 정렬 순서 또는 매개 변수를 제공한 것 외에도 레코드 집합의 선택 영역을 사용자 지정 하려면 다음 작업을 수행할 수 있습니다.  
  
-   에 사용자 지정 SQL 문자열을 전달 **lpszSQL** 호출 하는 경우 [열려](../../mfc/reference/crecordset-class.md#open) 레코드 집합에 대 한 합니다. 에 전달 하는 아무 것도 **lpsqSQL** 무엇 보다 우선는 [GetDefaultSQL](../../mfc/reference/crecordset-class.md#getdefaultsql) 멤버 함수를 반환 합니다.  
  
     자세한 내용은 참조 [SQL: 사용자 지정 레코드 집합의 SQL 문 (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md), 종류를 설명 하는 SQL 문 (또는 부분 문)를 전달할 수 있습니다 **열려** 프레임 워크에서 수행 하는 작업 및 이러한 합니다.  
  
    > [!NOTE]
    >  전달 하 여 사용자 지정 문자열 "SELECT" 또는 "{CALL"로 시작 하지 않으므로, MFC 테이블 이름이 포함 된 것으로 간주 됩니다. 이 다음 글머리 기호 항목에도 적용 됩니다.  
  
-   마법사가 레코드 집합의에서 작성 하는 문자열을 alter `GetDefaultSQL` 멤버 함수입니다. 함수의 반환 값을 변경 하는 코드를 편집 합니다. 기본적으로 마법사가 작성 한 `GetDefaultSQL` 단일 테이블 이름을 반환 하는 함수입니다.  
  
     사용할 수 있습니다 `GetDefaultSQL` 에 전달할 수 있는 항목 중 하나를 반환할는 **lpszSQL** 매개 변수를 **열려**합니다. 사용자 지정 SQL 문자열에 전달 하지 않으면 **lpszSQL**, 문자열을 사용 하는 프레임 워크는 `GetDefaultSQL` 반환 합니다. 여기에 최소한 `GetDefaultSQL` 단일 테이블 이름을 반환 해야 합니다. 전체 여러 테이블 이름을 반환 하 고 사용할 수 있습니다 하지만 **선택** 문에서 ODBC **호출** 문, 및 기타 등등. 에 전달할 수 목록은 **lpszSQL** -수도 있고 `GetDefaultSQL` 반환-참조 [SQL: 사용자 지정 레코드 집합의 SQL 문 (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md)합니다.  
  
     두 개 이상의 테이블의 조인을 수행 하는 경우 다시 작성 `GetDefaultSQL` SQL에서 사용 되는 테이블 목록을 사용자 지정 하려면 **FROM** 절. 자세한 내용은 참조 [레코드 집합: 조인 수행 (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md)합니다.  
  

-   수동으로 추가 필드 데이터 멤버, 가져와야 스키마에 대 한 데이터 원본의 런타임에 정보에 기반을 바인딩하십시오. 레코드 집합 클래스에 필드 데이터 멤버를 추가한 [RFX](../../data/odbc/record-field-exchange-using-rfx.md) 하거나 대량 RFX 함수를 호출 하 여는 [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) 또는 [DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange) 멤버 함수 및 클래스 생성자에서 데이터 멤버의 초기화 합니다. 자세한 내용은 참조 [레코드 집합: 데이터 열 동적 바인딩 (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)합니다.  
  
-   와 같은 레코드 집합 멤버 함수를 재정의 `OnSetOptions`, 응용 프로그램별 옵션을 설정 하거나 기본값을 재정의 합니다.  
  
 복잡 한 SQL 문을 기반으로 레코드 집합 하려는 경우 이러한 사용자 지정 기술 함께 사용 해야 합니다. 예를 들어 SQL 절을 사용 하려는 아마도 및 키워드 직접 지원 되지 않는 등이 있습니다 또는 레코드 집합에서 여러 테이블 조인 하는 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [레코드 집합 (ODBC)](../../data/odbc/recordset-odbc.md)   
 [레코드 집합: 레코드 집합 업데이트 레코드 방법 (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)   
 [ODBC 기초](../../data/odbc/odbc-basics.md)   
 [SQL](../../data/odbc/sql.md)   
 [레코드 집합: 레코드 잠금(ODBC)](../../data/odbc/recordset-locking-records-odbc.md)