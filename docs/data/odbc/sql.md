---
title: "SQL | Microsoft Docs"
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
  - "데이터베이스 클래스[C++], SQL 문"
  - "ODBC[C++], SQL 구현"
  - "SQL[C++]"
  - "SQL[C++], ODBC"
ms.assetid: e3923bc4-b317-4e0b-afd8-3cd403eb0faf
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# SQL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

SQL \(Structured Query Language\) is a way to communicate with a relational database that lets you define, query, modify, and control the data.  SQL 구문을 사용하면 지정한 기준에 따라 레코드를 추출하는 문을 생성할 수 있습니다.  
  
> [!NOTE]
>  이 내용은 MFC ODBC 클래스에 적용됩니다.  MFC DAO 클래스를 사용하려면 DAO 도움말의 Microsoft Jet 데이터베이스 엔진 SQL과 ANSI SQL의 비교 항목을 참조하십시오.  
  
 SQL 문은 **CREATE** 또는 **SELECT**와 같은 동사 키워드로 시작합니다.  SQL은 단일 문을 전체 테이블에 적용할 수 있는 강력한 언어입니다.  
  
 SQL에는 각각 특정 DBMS를 염두에 두고 개발된 다양한 버전이 있습니다.  MFC 데이터베이스 클래스는 X\/Open 및 SQL 액세스 그룹 CAE\(공통 응용 프로그램 환경\)의 SQL 초안 규격\(1991\)을 따르는 SQL 문을 인식합니다.  이 구문에 대한 자세한 내용은 MSDN LIBRARY CD의 *ODBC SDK* *Programmer's Reference*에 나오는 부록 C를 참조하십시오.  
  
 다음은 이 항목에서 설명하는 내용입니다.  
  
-   [ODBC와 SQL의 관계](#_core_open_database_connectivity_.28.odbc.29).  
  
-   [데이터베이스 클래스에서 사용하는 가장 일반적인 SQL 키워드](#_core_the_database_classes).  
  
-   [데이터베이스 클래스가 SQL을 사용하는 방법](#_core_how_the_database_classes_use_sql).  
  
##  <a name="_core_open_database_connectivity_.28.odbc.29"></a> ODBC\(Open Database Connectivity\)  
 데이터베이스 클래스는 SQL 명령을 코드에 포함시키는 대신 호출 단계 인터페이스에서 SQL을 사용하는 ODBC로 구현되어 있습니다.  ODBC는 ODBC 드라이버를 통해 [데이터 소스](../../data/odbc/data-source-odbc.md)와 통신할 때 SQL을 사용합니다.  이 드라이버는 SQL을 해석하고 필요한 경우 이를 Microsoft Access와 같은 특정 데이터베이스 형식에 사용할 수 있도록 변환합니다.  ODBC의 SQL 사용 방법에 대한 자세한 내용은 [ODBC](../../data/odbc/odbc-basics.md) 및 MSDN Library CD의 ODBC SDK *Programmer's Reference*를 참조하십시오.  
  
##  <a name="_core_the_database_classes"></a> 데이터베이스 클래스  
 데이터베이스 클래스는 기존의 [데이터 소스](../../data/odbc/data-source-odbc.md)에서 데이터를 조작하고 업데이트할 수 있도록 고안된 것입니다.  [MFC 응용 프로그램 마법사](../../mfc/reference/database-support-mfc-application-wizard.md), [MFC ODBC 소비자 마법사](../../mfc/reference/adding-an-mfc-odbc-consumer.md)\(**클래스 추가**를 통해 액세스\) 및 데이터베이스 클래스가 대부분의 SQL 문을 생성합니다.  
  
 데이터베이스 클래스는 SQL의 일부인 DML\(데이터 조작 언어\)을 사용합니다.  이 명령을 사용하면 데이터 소스 전체 또는 일부를 조작하고 레코드를 새로 추가하고 편집하고 삭제할 수 있습니다.  다음 표는 가장 일반적인 SQL 키워드 및 데이터베이스 클래스가 이 키워드를 사용하는 방법을 보여 줍니다.  
  
### 일반적인 SQL 키워드  
  
|SQL 키워드|마법사 및 데이터베이스 클래스의 키워드 사용 용도|  
|-------------|---------------------------------|  
|**SELECT**|데이터 소스에서 사용할 테이블 및 열을 지정|  
|**WHERE**|선택 범위를 좁히는 필터 적용|  
|**ORDER BY**|레코드 집합에 정렬 순서 적용|  
|**Insert**|레코드 집합에 새 레코드 추가|  
|**Delete**|레코드 집합에서 레코드 삭제|  
|**UPDATE**|레코드의 필드 수정|  
  
 또한 데이터베이스 클래스는 일부 데이터 소스에 대해 미리 정의된 쿼리\(또는 저장 프로시저\)를 호출하는 데 사용되는 ODBC **CALL** 문을 인식합니다.  ODBC 데이터베이스 드라이버는 이 문을 해석하여 각 DBMS에 알맞은 명령으로 대체합니다.  
  
> [!NOTE]
>  일부 DBMS는 **CALL** 문을 지원하지 않습니다.  
  
 `CRecordset::Open`에서 사용자가 제공한 문을 클래스가 인식할 수 없는 경우에는 해당 문이 테이블 이름으로 해석됩니다.  
  
 프레임워크가 SQL 문을 생성하는 방법에 대한 자세한 설명은 [레코드 집합: 레코드 집합의 레코드 선택 방법\(ODBC\)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md) 및 [SQL: 레코드 집합의 SQL 문 사용자 지정\(ODBC\)](../../data/odbc/sql-customizing-your-recordset’s-sql-statement-odbc.md)을 참조하십시오.  
  
 SQL 데이터베이스는 C 및 C\+\+에 사용되는 것과 유사한 데이터 형식을 사용합니다.  이 데이터 형식의 유사점에 대한 자세한 내용은 [SQL: SQL 및 C\+\+ 데이터 형식\(ODBC\)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)을 참조하십시오.  
  
 MSDN LIBRARY CD의 ODBC SDK 프로그래머 참조에서는 지원되는 SQL 문, 데이터 형식, SQL 핵심 문법, SQL에 대한 권장 도서 목록 등을 비롯하여 SQL에 대한 자세한 내용을 볼 수 있습니다.  
  
##  <a name="_core_how_the_database_classes_use_sql"></a> 데이터베이스 클래스가 SQL을 사용하는 방법  
 데이터베이스 클래스에서 파생된 레코드 집합은 ODBC를 사용하여 데이터 소스와 통신하고 ODBC는 SQL 문을 보내 데이터 소스에서 레코드를 검색합니다.  이 항목에서는 데이터베이스 클래스와 SQL의 관계에 대해 설명합니다.  
  
 레코드 집합은 SQL 문의 여러 부분을 하나의 `CString`으로 빌드하여 SQL 문을 생성하고  해당 문자열은 레코드 집합을 반환하는 **SELECT** 문으로 생성됩니다.  
  
 레코드 집합이 ODBC를 호출하여 데이터 소스에 SQL 문을 보내면 ODBC 드라이버 관리자가 이 문을 ODBC 드라이버에 전달하고 ODBC 드라이버는 이 문을 내부 DBMS로 보냅니다.  DBMS는 결과 레코드 집합을 반환하고 ODBC 드라이버는 응용 프로그램에 이 레코드를 반환합니다.  데이터베이스 클래스는 `CRecordset`에서 파생된 형식이 안전한 C\+\+ 클래스의 결과 집합을 사용자의 프로그램에서 액세스할 수 있도록 합니다.  
  
 데이터베이스 클래스가 SQL을 사용하는 방법에 대한 자세한 내용은 다음 항목을 참조하십시오.  
  
-   [SQL: 레코드 집합의 SQL 문 사용자 지정\(ODBC\)](../../data/odbc/sql-customizing-your-recordset’s-sql-statement-odbc.md)  
  
-   [SQL: SQL 및 C\+\+ 데이터 형식\(ODBC\)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)  
  
-   [SQL: SQL 직접 호출\(ODBC\)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)  
  
## 참고 항목  
 [ODBC\(Open Database Connectivity\)](../../data/odbc/open-database-connectivity-odbc.md)   
 [ODBC 기초](../../data/odbc/odbc-basics.md)