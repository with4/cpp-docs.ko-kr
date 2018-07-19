---
title: SQL | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- database classes [C++], SQL statements
- SQL [C++]
- SQL [C++], ODBC
- ODBC [C++], SQL implementation
ms.assetid: e3923bc4-b317-4e0b-afd8-3cd403eb0faf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: df1563d8bb3d53bb405fbb0d89b2b26cc964bd44
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33093245"
---
# <a name="sql"></a>SQL
SQL (구조적 쿼리 언어)은 쿼리를 정의 수정 및 데이터를 제어할 수 있는 관계형 데이터베이스와 통신 하는 방법입니다. SQL 구문을 사용 하 여, 사용자가 지정한 조건에 따라 레코드를 추출 하는 문을 생성할 수 있습니다.  
  
> [!NOTE]
>  이 정보는 MFC ODBC 클래스에 적용 됩니다. MFC DAO 클래스와 함께 작업 하는 경우에 비교의 Microsoft Jet 데이터베이스 엔진이 SQL 항목 및 DAO 도움말의 ANSI SQL 참조 하십시오.  
  
 SQL 문을 키워드 동사와 같은 시작 **만들기** 또는 **선택**합니다. SQL은 매우 강력한 언어입니다. 단일 문에 전체 테이블에 영향을 줄 수 있습니다.  
  
 다양 한 SQL 버전이 각각를 개발 된 특정 DBMS에 주의 합니다. MFC 데이터베이스 클래스에는 X / Open을 해당 하는 SQL 문 및 SQL 액세스 그룹 일반적인 응용 프로그램 환경 (CAE) SQL 초안 사양을 (1991) 집합을 인식 합니다. 이 명령문의 정보는 구문에 대 한 참조에서 부록 C는 *ODBC SDK* *Programmer's Reference* MSDN 라이브러리 CD에 있습니다.  
  
 이 항목에 설명 합니다.  
  
-   [ODBC와 SQL 간의 관계](#_core_open_database_connectivity_.28.odbc.29)합니다.  
  
-   [데이터베이스 클래스에서 사용 하는 가장 일반적인 SQL 키워드](#_core_the_database_classes)합니다.  
  
-   [데이터베이스 클래스는 SQL을 사용 하는 방법을](#_core_how_the_database_classes_use_sql)합니다.  
  
##  <a name="_core_open_database_connectivity_.28.odbc.29"></a> Open Database Connectivity (ODBC)  
 데이터베이스 클래스는 코드에서 SQL 명령을 포함 하는 것이 아니라 호출 수준 인터페이스에서 SQL을 사용 하는 ODBC로 구현 됩니다. ODBC SQL을 사용 하 여 통신할 수는 [데이터 원본](../../data/odbc/data-source-odbc.md) ODBC 드라이버를 통해. 이러한 드라이버는 SQL을 해석 하 고 Microsoft Access와 같은 특정 데이터베이스 형식으로 사용 하기 위해 필요한 경우 변환 합니다. ODBC SQL을 사용 하는 방법에 대 한 자세한 내용은 참조 [ODBC](../../data/odbc/odbc-basics.md) 및 ODBC SDK *Programmer's Reference* MSDN 라이브러리 CD에 있습니다.  
  
##  <a name="_core_the_database_classes"></a> 데이터베이스 클래스  
 데이터베이스 클래스 조작 하 고 기존 데이터를 업데이트할 수 있도록 고안 된 [데이터 소스](../../data/odbc/data-source-odbc.md)합니다. [MFC 응용 프로그램 마법사](../../mfc/reference/database-support-mfc-application-wizard.md), [MFC ODBC 소비자 마법사](../../mfc/reference/adding-an-mfc-odbc-consumer.md) (통해 액세스 **클래스 추가**), 및 데이터베이스 클래스 사용자에 대 한 대부분의 SQL 문 작성 합니다.  
  
 데이터베이스 클래스는 SQL 데이터 조작 언어 (dml)의 일부를 사용 합니다. 이러한 명령은 전체 또는 일부 데이터 원본의 사용, 새 레코드를 추가, 레코드를 편집 및 레코드를 삭제할 수 있습니다. 다음 표에서 가장 일반적인 SQL 키워드는 방법과 데이터베이스 클래스 사용 합니다.  
  
### <a name="some-common-sql-keywords"></a>몇 가지 일반적인 SQL 키워드  
  
|SQL 키워드|마법사 및 데이터베이스 클래스 사용|  
|-----------------|---------------------------------------------|  
|**SELECT**|테이블 및 데이터 원본의 열은 데 사용할 식별.|  
|**WHERE**|선택 영역을 범위를 좁히는 필터를 적용 합니다.|  
|**ORDER BY**|레코드 집합에 정렬 순서를 적용 합니다.|  
|**삽입**|레코드 집합에 새 레코드를 추가 합니다.|  
|**삭제**|레코드 집합에서 레코드를 삭제 합니다.|  
|**업데이트**|레코드의 필드를 수정 합니다.|  
  
 데이터베이스 클래스에서 ODBC를 인식 하는 또한 **호출** 일부 데이터 소스에 대해 미리 정의 된 쿼리 (또는 저장된 프로시저)를 호출 하는 데 사용할 수 있는 문. ODBC 데이터베이스 드라이버는 이러한 문을 해석 하 고 각 DBMS에 적절 한 명령을 대체 합니다.  
  
> [!NOTE]
>  일부 Dbms 지원 **호출** 문.  
  
 클래스에서 사용자가 제공한 문을 인식할 수 없는 경우 `CRecordset::Open`, 테이블 이름으로 해석 됩니다.  
  
 참조에 대 한 설명은 프레임 워크 SQL 문을 생성 하는 방법, [레코드 집합: 레코드 집합의 레코드 선택 방법 (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md) 및 [SQL: 사용자 지정 레코드 집합의 SQL 문 (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md)합니다.  
  
 SQL 데이터베이스에는 C 및 c + +에서 사용 하는 것과 유사한 데이터 형식을 사용 합니다. 이러한 유사성의 논의 알려면 [SQL: SQL 및 c + + 데이터 형식 (ODBC)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)합니다.  
  
 지원 되는 SQL 문, 데이터 형식, SQL 핵심 문법 및 읽기 목록이 SQL에 대 한 권장된 게시 목록을 비롯 한 SQL에 대 한 자세한 정보를 확인할 수는 *ODBC SDK* *프로그래머 참조*  MSDN 라이브러리 CD에 있습니다.  
  
##  <a name="_core_how_the_database_classes_use_sql"></a> 데이터베이스 클래스는 SQL을 사용 하는 방법  
 데이터베이스 클래스에서 파생 된 레코드 집합에서 ODBC를 사용 하 여 데이터 소스와 통신 하 고 ODBC SQL 문을 전송 하 여 데이터 원본에서 레코드를 검색 합니다. 이 항목에서는 데이터베이스 클래스와 SQL 간의 관계를 설명 합니다.  
  
 레코드 집합에 SQL 문으로 부분을 작성 하 여 SQL 문을 생성 한 `CString`합니다. 해당 문자열으로 생성 됩니다는 **선택** 레코드 집합을 반환 하는 문입니다.  
  
 레코드 집합에서 ODBC 데이터 원본에는 SQL 문을 보내는를 호출 하면 ODBC 드라이버 관리자에서 ODBC 드라이버에는 문을 전달 하 고 드라이버 원본 DBMS에 보냅니다. DBMS의 레코드에 대 한 결과 집합을 반환 하 고 ODBC 드라이버 응용 프로그램에 레코드를 반환 합니다. 데이터베이스 클래스에서 파생 된 형식이 안전한 c + + 클래스에 결과 집합에 프로그램 액세스할 수 있도록 `CRecordset`합니다.  
  
 다음 항목에서는 데이터베이스 클래스는 SQL을 사용 하는 방법에 대 한 자세한 정보가 표시 됩니다.  
  
-   [SQL: 레코드 집합의 SQL 문 (ODBC) 사용자 지정](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md)  
  
-   [SQL: SQL 및 C++ 데이터 형식(ODBC)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)  
  
-   [SQL: SQL 직접 호출(ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)  
  
## <a name="see-also"></a>참고 항목  
 [Open Database Connectivity (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)   
 [ODBC 기본 사항](../../data/odbc/odbc-basics.md)