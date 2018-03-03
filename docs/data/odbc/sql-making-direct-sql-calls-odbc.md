---
title: "SQL: SQL 직접 호출 (ODBC)을 수행한 | Microsoft Docs"
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
- SQL, direct calls from ODBC
- SQL, calling directly from ODBC
- ODBC, SQL calls
- SQL calls
- direct SQL calls from ODBC
ms.assetid: 091988d2-f5a5-4c2d-aa09-8779a9fb9607
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4c5debd5017c2c9c9cad240f831fdf6e02be98ef
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="sql-making-direct-sql-calls-odbc"></a>SQL: SQL 직접 호출(ODBC)
이 항목에 설명 합니다.  
  
-   SQL 직접 사용 하는 경우 호출 합니다.  
  
-   [데이터 원본에 대 한 호출이 SQL 직접 만드는 방법을](#_core_making_direct_sql_function_calls)합니다.  
  
> [!NOTE]
>  이 정보는 MFC ODBC 클래스에 적용 됩니다. MFC DAO 클래스와 함께 작업 하는 경우 "비교의 Microsoft Jet 데이터베이스 엔진이 SQL 및 ANSI SQL" DAO 도움말의 항목을 참조 하십시오.  
  
##  <a name="_core_when_to_call_sql_directly"></a>SQL 직접 호출 하는 경우  
 새 테이블을 만들려면 (delete) 테이블을 삭제, 기존 테이블 변경, 인덱스 만들기 및 변경 하는 다른 SQL 기능을 수행할는 [데이터 원본 (ODBC)](../../data/odbc/data-source-odbc.md) 스키마 데이터베이스를 사용 하 여 데이터 원본에 직접 SQL 문을 실행 해야 합니다 정의 언어 (DDL)입니다. 마법사를 사용 하 여 디자인 타임에는 테이블에 대 한 레코드 집합을 만들 때에 레코드 집합의 나타내기 위해 테이블의 어떤 열을 선택할 수 있습니다. 데이터 소스의 사용자 나중에 추가할 테이블, 프로그램 컴파일된 후 열에 대 한 허용 하지 않습니다. 데이터베이스 클래스 DDL에 직접 지원 하지 않지만 런타임에 새 열을 레코드 집합에 동적으로 바인딩하는 코드를 작성할 수 있습니다. 이 바인딩을 수행 하는 방법에 대 한 정보를 참조 하십시오. [레코드 집합: 동적으로 바인딩 데이터 열 (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)합니다.  
  
 스키마 또는 DDL 함수를 수행할 수 있는 다른 도구를 변경 하는 DBMS를 사용할 수 있습니다. 또한 레코드를 반환 하지 않는 한 미리 정의 된 쿼리 (저장된 프로시저)를 호출 하는 등 SQL 문을 보내기 위한 ODBC 함수 호출을 사용할 수 있습니다.  
  
##  <a name="_core_making_direct_sql_function_calls"></a>직접 SQL 함수 호출 만들기  
 직접 사용 하 여 SQL 호출을 실행할 수 있습니다는 [CDatabase 클래스](../../mfc/reference/cdatabase-class.md) 개체입니다. SQL 문 문자열을 설정 (에 일반적으로 `CString`)에 전달 하 고는 [CDatabase::ExecuteSQL](../../mfc/reference/cdatabase-class.md#executesql) 의 멤버 함수 프로그램 `CDatabase` 개체입니다. ODBC 함수 호출을 사용 하 여 일반적으로 레코드를 반환 하는 SQL 문을 보내기는 레코드는 무시 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [SQL](../../data/odbc/sql.md)