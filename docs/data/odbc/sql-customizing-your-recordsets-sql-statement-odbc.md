---
title: "SQL: 레코드 집합의 SQL 문 (ODBC) 사용자 지정 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- recordsets, SQL statements
- ODBC recordsets, SQL statements
- SQL statements, customizing
- SQL statements, recordset
- customizing SQL statements
- overriding, SQL statements
- SQL, opening recordsets
ms.assetid: 72293a08-cef2-4be2-aa1c-30565fcfbaf9
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3099fbf6b97f3ad18a28c071fcd08ec8280fa24a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="sql-customizing-your-recordsets-sql-statement-odbc"></a>SQL: 레코드 집합의 SQL 문 사용자 지정(ODBC)
이 항목에 설명 합니다.  
  
-   프레임 워크 SQL 문을 생성 하는 방법  
  
-   SQL 문의 재정의 하는 방법  
  
> [!NOTE]
>  이 정보는 MFC ODBC 클래스에 적용 됩니다. MFC DAO 클래스와 함께 작업 하는 경우 "비교의 Microsoft Jet 데이터베이스 엔진이 SQL 및 ANSI SQL" DAO 도움말의 항목을 참조 하십시오.  
  
## <a name="sql-statement-construction"></a>SQL 문 생성  
 레코드 집합 기반 SQL에서 주로 레코드 선택 **선택** 문. 재정의 된 버전의 마법사와 함께 클래스를 선언 하는 경우 기록 된 `GetDefaultSQL` 다음과 같은 멤버 함수 (레코드 집합 클래스에 대 한 호출 `CAuthors`).  
  
```  
CString CAuthors::GetDefaultSQL()  
{  
    return "AUTHORS";  
}  
```  
  
 이 재정의 기본적으로 마법사를 사용 하 여 지정한 테이블 이름을 반환 합니다. 예제에서는 테이블 이름이 "작성자"입니다. 나중에 호출 하는 경우 레코드 집합의 **열려** 멤버 함수 **열려** 최종 생성 **선택** 문의 폼의:  
  
```  
SELECT rfx-field-list FROM table-name [WHERE m_strFilter]   
       [ORDER BY m_strSort]  
```  
  
 여기서 `table-name` 호출 하 여 가져온 `GetDefaultSQL` 및 `rfx-field-list` RFX 함수 호출에서 가져온 `DoFieldExchange`합니다. 이에 대 한 결과가 **선택** 문을 바꾼 경우가 아니라면 것 재정의 실행 시 매개 변수 또는 필터를 사용 하 여 기본 문을 수정할 수도 있습니다.  
  
> [!NOTE]
>  공백이 포함 (또는 포함 될 수) 하는 열 이름을 지정 하면 이름을 대괄호로 묶어야 합니다. 예를 들어, "이름" 이름 "[이름]" 해야 합니다.  
  
 기본값을 재정의 하려면 **선택** 문, 전체를 포함 하는 문자열의 패스 **선택** 문을 호출 하는 경우 **열려**합니다. 레코드 집합 자체 기본 문자열을 생성 하는 대신 제공 문자열을 사용 합니다. 대체 문에 포함 된 경우는 **여기서** 절에서 한 필터를 지정 하지 않으면 **m_strFilter** 하는 두 개의 문을 필터링 합니다. 마찬가지로, 대체 문에 포함 된 경우는 **ORDER BY** 절에 정렬을 지정 하지 않으면 `m_strSort` 2 개의 정렬 문이 보유 하지 것입니다.  
  
> [!NOTE]
>  필터 (또는 SQL 문의 다른 부분)에서 리터럴 문자열을 사용 하는 경우 "인용 부호" 해야 할 수 있습니다 (지정 된 구분 기호로 포함) 이러한 문자열 리터럴 및 DBMS 관련 리터럴 접두사와 접미사 문자 (또는 문자)입니다.  
  
 DBMS에 따라 외부 조인과 같은 작업에 대 한 구문 특별 한 요구도 발생할 수 있습니다. ODBC 함수를 사용 하 여 DBMS에 대 한 드라이버에서이 정보를 얻을 수 있습니다. 예를 들어 호출 **:: SQLGetTypeInfo** 특정 데이터 형식에 대 한 같은 **SQL_VARCHAR**, 요청 하는 **LITERAL_PREFIX** 및 **LITERAL_SUFFIX** 문자입니다. 데이터베이스에 독립적인 코드를 작성 하는 경우 참조에서 부록 C는 *ODBC SDK**Programmer's Reference* 자세한 구문 정보에 대 한 MSDN 라이브러리 CD에 있습니다.  
  
 레코드 집합 개체에는 레코드를 선택 하 여 사용자 지정 SQL 문을 전달 하지 않으면 사용 하는 SQL 문을 생성 합니다. 주로에 전달 하는 값에 따라 달라 집니다 방식은 `lpszSQL` 의 매개 변수는 **열려** 멤버 함수입니다.  
  
 SQL의 일반적인 형식은 **선택** 문이:  
  
```  
SELECT [ALL | DISTINCT] column-list FROM table-list  
    [WHERE search-condition][ORDER BY column-list [ASC | DESC]]  
```  
  
 추가 하는 한 가지 방법은 **DISTINCT** 레코드 집합의 SQL 문에 키워드의 첫 번째 RFX 함수 호출에 키워드를 포함 하는 것 `DoFieldExchange`합니다. 예:  
  
```  
...  
    RFX_Text(pFX, "DISTINCT CourseID", m_strCourseID);  
...  
```  
  
> [!NOTE]
>  읽기 전용으로 연 레코드 집합에만이 방법을 사용 합니다.  
  
## <a name="overriding-the-sql-statement"></a>SQL 문을 재정의  
 다음 표에서 예를 보여 줍니다.는 `lpszSQL` 매개 변수를 **열려**합니다. 사례 테이블에는 표 다음에 설명 되어 있습니다.  
  
 **LpszSQL 매개 변수 및 결과 SQL 문자열**  
  
|Case|LpszSQL에 전달|결과 SELECT 문에|  
|----------|------------------------------|------------------------------------|  
|1|**NULL**|**선택** *rfx 필드 목록* **FROM** *테이블 이름*<br /><br /> `CRecordset::Open`호출 `GetDefaultSQL` 테이블 이름을 가져오지 못했습니다. 결과 문자열은 다음 중 한 경우 2 ~ 5, 물품에 따라 `GetDefaultSQL` 반환 합니다.|  
|2|테이블 이름|**선택** *rfx 필드 목록* **FROM** *테이블 이름*<br /><br /> 필드 목록에 있는 RFX 문은에서 가져온 것 `DoFieldExchange`합니다. 경우 **m_strFilter** 및 `m_strSort` 비어 있지 않으며, 추가는 **여기서** 및/또는 **ORDER BY** 절.|  
|3 *|전체 **선택** 문 없이 **여기서** 또는 **ORDER BY** 절|성공 합니다. 경우 **m_strFilter** 및 `m_strSort` 비어 있지 않으며, 추가는 **여기서** 및/또는 **ORDER BY** 절.|  
|4 *|전체 **선택** 문을 **여기서** 및/또는 **ORDER BY** 절|성공 합니다. **m_strFilter** 및/또는 `m_strSort` 해야 비어 있거나 두 개의 필터 유지 및/또는 정렬 문이 생성 됩니다.|  
|5 *|저장된 프로시저에 대 한 호출|성공 합니다.|  
  
 \*`m_nFields` 에 지정 된 열 개수 보다 작거나 같아야 합니다는 **선택** 문. 에 지정 된 각 열의 데이터 형식을 **선택** 문은 해당 되는 RFX 출력 열의 데이터 형식과 동일 해야 합니다.  
  
### <a name="case-1---lpszsql--null"></a>사례 1 lpszSQL = NULL  
 레코드 집합 선택에 따라 달라 집니다 `GetDefaultSQL` 될 때 반환 `CRecordset::Open` 에서 호출 합니다. 2 ~ 5의 경우 가능한 문자열을 설명 합니다.  
  
### <a name="case-2---lpszsql--a-table-name"></a>사례 2 lpszSQL = 테이블 이름  
 레코드 집합 레코드 필드 교환 (RFX)를 사용 하 여 목록을 작성 하는 열의 열 이름에서는 RFX 함수 호출의 레코드 집합 클래스의 재정의에 제공 된 `DoFieldExchange`합니다. 레코드 집합 클래스를 선언 하는 마법사를 사용 하는 경우 (제공 하는 마법사에서 지정한 같은 테이블 이름을 전달) 사례 1과 같은 결과가 생깁니다. 사례 2 여 클래스를 작성 하는 마법사를 사용 하지 않는 경우 SQL 문을 생성 하는 가장 간단한 방법.  
  
 다음 예제에서는 MFC 데이터베이스 응용 프로그램에서 레코드를 선택 하는 SQL 문을 생성 합니다. 프레임 워크에서 호출 하는 경우는 `GetDefaultSQL` 멤버 함수의 경우 함수는 테이블의 이름을 반환 `SECTION`합니다.  
  
```  
CString CEnrollSet::GetDefaultSQL()  
{  
    return "SECTION";  
}  
```  
  
 SQL에 대 한 열의 이름을 가져오는 **선택** 문, 프레임 워크를 호출 하 여는 `DoFieldExchange` 멤버 함수입니다.  
  
```  
void CEnrollSet::DoFieldExchange(CFieldExchange* pFX)  
{  
    pFX->SetFieldType(CFieldExchange::outputColumn);  
    RFX_Text(pFX, "CourseID", m_strCourseID);  
    RFX_Text(pFX, "InstructorID", m_strInstructorID);  
    RFX_Text(pFX, "RoomNo", m_strRoomNo);  
    RFX_Text(pFX, "Schedule", m_strSchedule);  
    RFX_Text(pFX, "SectionNo", m_strSectionNo);  
}  
```  
  
 완료 되 면 SQL 문을 다음과 같이 보입니다.  
  
```  
SELECT CourseID, InstructorID, RoomNo, Schedule, SectionNo   
    FROM SECTION  
```  
  
### <a name="case-3---lpszsql--a-selectfrom-statement"></a>사례 3 lpszSQL = SELECT 문에서 /  
 자동으로 생성 하는 rfx 대신 열 목록을 직접 지정 합니다. 이 경우 작업을 수행 하 여 설정할 수 있습니다.  
  
-   지정 하려는 **DISTINCT** 키워드 다음 **선택**합니다.  
  
     열 목록은 일치 해야 열 이름 및 형식과 같은 순서로 나열 된 것과 `DoFieldExchange`합니다.  
  
-   ODBC 함수를 사용 하 여 열 값을 수동으로 검색 해야 이유가 **:: SQLGetData** rfx를 바인딩하고 있습니다에 대 한 열을 검색 하는 대신 합니다.  
  
     예를 들어 응용 프로그램의 고객은 응용 프로그램을 배포한 후 데이터베이스 테이블에 추가 하는 새 열에 맞게 중지할 수 있습니다. 마법사를 사용 하 여 클래스를 선언 하는 시간에 인식 되지 않았으므로 이러한 추가 필드 데이터 멤버를 추가 해야 합니다.  
  
     열 목록은 일치 해야 열 이름 및 형식과 같은 순서로 나열 된 것과 `DoFieldExchange`직접 바인딩한 열 이름에 이어집니다. 자세한 내용은 참조 [레코드 집합: 데이터 열 동적 바인딩 (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)합니다.  
  
-   여러 테이블을 지정 하 여 테이블을 조인 하려면는 **FROM** 절.  
  
     내용 및 예제에 대 한 참조 [레코드 집합: 조인 수행 (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md)합니다.  
  
### <a name="case-4---lpszsql--selectfrom-plus-where-andor-order-by"></a>4 대/소문자 lpszSQL 선택 = / FROM 및 WHERE 또는 ORDER BY  
 모든 항목을 지정: 열 목록 (RFX 호출에 따라 `DoFieldExchange`)의 내용과 테이블 목록에서 한 **여기서** 및/또는 **ORDER BY** 절. 지정 하는 경우 프로그램 **여기서** 및/또는 **ORDER BY** 절이 방식이으로 사용 하지 않는 **m_strFilter** 및/또는 `m_strSort`합니다.  
  
### <a name="case-5---lpszsql--a-stored-procedure-call"></a>5 대/소문자 lpszSQL = 저장 프로시저 호출  
 미리 정의 된 쿼리 (예: Microsoft SQL Server 데이터베이스의 저장된 프로시저)를 호출 해야 하는 경우 작성 해야는 **호출** 에 전달할 문자열에는 문을 `lpszSQL`합니다. 마법사 미리 정의 된 쿼리를 호출 하기 위한 레코드 집합 클래스를 선언 하는 것을 지원 하지 않습니다. 모든 미리 정의 된 쿼리에 레코드를 반환 합니다.  
  
 미리 정의 된 쿼리 레코드를 반환 하지 않는 경우 사용할 수 있습니다는 `CDatabase` 멤버 함수 `ExecuteSQL` 직접 합니다. 에 대 한 레코드를 반환 하는 미리 정의 된 쿼리를 수동으로 작성 해야 호출 하는 RFX `DoFieldExchange` 모든 열에 대 한 프로시저에서 반환 합니다. RFX 호출 같은 순서 여야 하 고 미리 정의 된 쿼리로 동일한 형식을 반환 해야 합니다. 자세한 내용은 참조 [레코드 집합: 한 클래스에는 미리 정의 된 쿼리 (ODBC) 선언](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SQL: SQL 및 c + + 데이터 형식 (ODBC)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)   
 [SQL: SQL 직접 호출(ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)
