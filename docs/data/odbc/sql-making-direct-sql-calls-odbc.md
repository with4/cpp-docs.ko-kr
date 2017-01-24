---
title: "SQL: SQL 직접 호출(ODBC) | Microsoft Docs"
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
  - "ODBC에서 직접 SQL 호출"
  - "ODBC, SQL 호출"
  - "SQL 호출"
  - "SQL, ODBC에서 직접 호출"
  - "SQL, ODBC에서 직접 호출"
ms.assetid: 091988d2-f5a5-4c2d-aa09-8779a9fb9607
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SQL: SQL 직접 호출(ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

다음은 이 항목에서 설명하는 내용입니다.  
  
-   SQL을 직접 호출하는 경우  
  
-   [데이터 소스에 대한 SQL 함수를 직접 호출하는 방법](#_core_making_direct_sql_function_calls)  
  
> [!NOTE]
>  이 내용은 MFC ODBC 클래스에 적용됩니다.  MFC DAO 클래스를 사용하려면 DAO 도움말의 "Microsoft Jet 데이터베이스 엔진 SQL과 ANSI SQL의 비교" 항목을 참조하십시오.  
  
##  <a name="_core_when_to_call_sql_directly"></a> SQL을 직접 호출하는 경우  
 새 테이블 작성, 테이블 삭제, 기존 테이블 변경, 인덱스 만들기 및 [데이터 소스\(ODBC\)](../../data/odbc/data-source-odbc.md) 스키마를 변경하는 기타 SQL 함수를 수행하려면 DDL\(데이터베이스 정의 언어\)을 사용하여 데이터 소스에서 직접 SQL 문을 실행해야 합니다.  디자인 타임에서 마법사를 사용하여 테이블의 레코드 집합을 만드는 경우 레코드 집합에 표시할 테이블의 열을 사용자가 선택할 수 있습니다.  그러나 프로그램을 컴파일한 후에 사용자 또는 데이터 소스의 다른 사용자가 테이블에 추가한 열은 선택할 수 없습니다.  데이터베이스 클래스는 DDL을 직접 지원하지 않지만 런타임에서 새 열을 레코드 집합에 동적으로 바인딩하는 코드를 작성할 수는 있습니다.  이러한 바인딩 방법에 대한 자세한 내용은 [레코드 집합: 데이터 열 동적 바인딩\(ODBC\)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)을 참조하십시오.  
  
 DBMS를 사용하여 스키마를 변경하거나 DDL 함수를 수행할 수 있는 다른 도구를 사용할 수 있습니다.  또한 ODBC 함수 호출을 사용하여 SQL 문을 보낼 수도 있습니다. 예를 들면 레코드를 반환하지 않는 미리 정의된 쿼리\(저장 프로시저\)를 호출할 수 있습니다.  
  
##  <a name="_core_making_direct_sql_function_calls"></a> SQL 함수 직접 호출  
 [CDatabase Class](../../mfc/reference/cdatabase-class.md) 개체를 사용하여 SQL 호출을 직접 실행할 수 있습니다.  이렇게 하려면 SQL 문의 문자열\(대개 `CString`\)을 설정하고 이를 `CDatabase` 개체의 [CDatabase::ExecuteSQL](../Topic/CDatabase::ExecuteSQL.md) 멤버 함수에 전달하면 됩니다.  ODBC 함수 호출을 사용하여 정상적으로 레코드를 반환하는 SQL 문을 보내면 이 레코드는 무시됩니다.  
  
## 참고 항목  
 [SQL](../../data/odbc/sql.md)