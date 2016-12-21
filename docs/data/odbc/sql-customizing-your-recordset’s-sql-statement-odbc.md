---
title: "SQL: 레코드 집합의 SQL 문 사용자 지정(ODBC) | Microsoft Docs"
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
  - "SQL 문 사용자 지정"
  - "ODBC 레코드 집합, SQL 문"
  - "재정의, SQL 문"
  - "레코드 집합, SQL 문"
  - "SQL 문, 사용자 지정"
  - "SQL 문, 레코드 집합"
  - "SQL, 레코드 집합 열기"
ms.assetid: 72293a08-cef2-4be2-aa1c-30565fcfbaf9
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SQL: 레코드 집합의 SQL 문 사용자 지정(ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

다음은 이 항목에서 설명하는 내용입니다.  
  
-   프레임워크가 SQL 문을 생성하는 방법  
  
-   SQL 문을 재정의하는 방법  
  
> [!NOTE]
>  이 내용은 MFC ODBC 클래스에 적용됩니다.  MFC DAO 클래스를 사용하려면 DAO 도움말의 "Microsoft Jet 데이터베이스 엔진 SQL과 ANSI SQL의 비교" 항목을 참조하십시오.  
  
## SQL 문 생성  
 레코드 집합은 주로 SQL **SELECT** 문에 기반하여 레코드를 선택합니다.  마법사를 사용하여 클래스를 선언하면 마법사는 다음과 유사한 형태로 `GetDefaultSQL` 멤버 함수를 재정의합니다\(레코드 집합 클래스가 `CAuthors`인 경우\).  
  
```  
CString CAuthors::GetDefaultSQL()  
{  
    return "AUTHORS";  
}  
```  
  
 기본적으로, 이 재정의는 마법사를 사용하여 지정한 테이블 이름을 반환합니다.  이 예제에서 테이블 이름은 "AUTHORS"입니다. 나중에 레코드 집합의 **Open** 멤버 함수를 호출하면 다음과 같은 형식의 최종 **SELECT** 문이 생성됩니다.  
  
```  
SELECT rfx-field-list FROM table-name [WHERE m_strFilter]   
       [ORDER BY m_strSort]  
```  
  
 여기서 `table-name`은 `GetDefaultSQL`을 호출하여 구하고 `rfx-field-list`는 `DoFieldExchange`의 RFX 함수 호출을 통해 구합니다.  이것은 런타임에서 재정의하지 않은 경우 생성되는 **SELECT** 문이며 매개 변수 또는 필터를 사용하여 기본 문을 수정할 수도 있습니다.  
  
> [!NOTE]
>  공백을 포함한\(또는 포함할 수 있는\) 열 이름을 지정하는 경우 열 이름을 대괄호\(\[\]\)로 묶어야 합니다.  예를 들어, "First Name"이라는 이름은 "\[First Name\]"으로 표기합니다.  
  
 기본 **SELECT** 문을 재정의하려면 **Open**을 호출할 때 완전한 **SELECT** 문을 포함하는 문자열을 전달합니다.  이렇게 하면 레코드 집합이 자체 기본 문자열을 생성하는 대신 사용자가 입력한 문자열을 사용합니다.  대체 문에 **WHERE** 절이 포함되어 있는 경우 **m\_strFilter**에 필터를 지정하면 2개의 필터 문이 생기므로 **m\_strFilter**에는 필터를 지정하지 않아야 합니다.  마찬가지로, 대체 문에 **ORDER BY** 절이 포함되어 있는 경우에는 `m_strSort`에 정렬을 지정하지 않아야 2개의 정렬 문이 생기지 않습니다.  
  
> [!NOTE]
>  필터 또는 SQL 문의 다른 부분에 리터럴 문자열을 사용하는 경우에는 DBMS 전용 리터럴 접두 문자 및 리터럴 접미 문자가 포함된 해당 문자열을 "인용 부호" 또는 지정된 구분 기호로 묶어야 합니다.  
  
 DBMS에 따라서는 외부 조인과 같은 연산에 특수 구문이 필요할 수도 있습니다.  이 경우 ODBC 함수를 사용하여 DBMS의 드라이버에서 필요한 정보를 구합니다.  예를 들어, **LITERAL\_PREFIX** 및 **LITERAL\_SUFFIX** 문자를 요청하려면 **::SQLGetTypeInfo**를 호출하여 **SQL\_VARCHAR**와 같은 특정 데이터 형식에 대한 정보를 얻습니다.  데이터베이스 독립적인 코드를 작성하는 경우 자세한 구문 정보는 MSDN LIBRARY CD의 *ODBC SDK* 프로그래머 참조에 있는 부록 C를 참조하십시오.  
  
 사용자가 사용자 지정 SQL 문을 전달하지 않을 경우 레코드 집합 개체는 레코드를 선택하는 데 사용할 SQL 문을 생성합니다.  이 과정은 주로 사용자가 **Open** 멤버 함수의 `lpszSQL` 매개 변수에 전달한 값에 따라 달라집니다.  
  
 SQL **SELECT** 문의 일반적인 형식은 다음과 같습니다.  
  
```  
SELECT [ALL | DISTINCT] column-list FROM table-list  
    [WHERE search-condition][ORDER BY column-list [ASC | DESC]]  
```  
  
 **DISTINCT** 키워드를 레코드 집합의 SQL 문에 추가하는 한 가지 방법은 `DoFieldExchange`의 첫 번째 RFX 함수 호출에 해당 키워드를 포함시키는 것입니다.  예를 들면 다음과 같습니다.  
  
```  
...  
    RFX_Text(pFX, "DISTINCT CourseID", m_strCourseID);  
...  
```  
  
> [!NOTE]
>  이 방법은 레코드 집합이 읽기 전용으로 열려 있는 경우에만 사용합니다.  
  
## SQL 문 재정의  
 다음 표에서는 **Open**에 전달될 수 있는 `lpszSQL` 매개 변수 예를 보여 줍니다.  각 사례는 표 다음에 설명되어 있습니다.  
  
 **lpszSQL 매개 변수 및 결과 SQL 문자열**  
  
|Case|lpszSQL에 전달된 값|결과 SELECT 문|  
|----------|--------------------|-----------------|  
|1|**NULL**|**SELECT** rfx\-field\-list **FROM** table\-name<br /><br /> `CRecordset::Open`이 테이블 이름을 구하기 위해 `GetDefaultSQL`을 호출합니다.  결과 문자열은 사례 2부터 5 중 하나이며 `GetDefaultSQL`의 반환 값에 따라 다릅니다.|  
|2|테이블 이름|**SELECT** rfx\-field\-list **FROM** table\-name<br /><br /> `DoFieldExchange`의 RFX 문에서 필드 목록을 구합니다.  **m\_strFilter** 및 `m_strSort`가 비어 있지 않으면 **WHERE** 및\/또는 **ORDER BY** 절을 추가합니다.|  
|3 \*|**WHERE** 또는 **ORDER BY** 절이 없지만 완전한 **SELECT** 문|전달된 문과 동일  **m\_strFilter** 및 `m_strSort`가 비어 있지 않으면 **WHERE** 및\/또는 **ORDER BY** 절을 추가합니다.|  
|4 \*|**WHERE** 및\/또는 **ORDER BY** 절이 있는 완전한 **SELECT** 문|전달된 문과 동일  **m\_strFilter** 및\/또는 `m_strSort`가 비어 있어야 하며, 그렇지 않은 경우에는 2개의 필터 및\/또는 정렬 문이 생성됩니다.|  
|5 \*|저장 프로시저 호출|전달된 문과 동일|  
  
 \* `m_nFields`는 **SELECT** 문에 지정된 열의 수보다 작거나 같아야 합니다.  **SELECT** 문에 지정된 각 열의 데이터 형식은 해당되는 RFX 출력 열의 데이터 형식과 같아야 합니다.  
  
### 사례 1   lpszSQL \= NULL  
 레코드 집합 선택은 `CRecordset::Open`이 `GetDefaultSQL`을 호출할 때 `GetDefaultSQL`이 반환하는 값에 따라 달라집니다.  사례 2부터 사례 5까지는 가능한 문자열을 설명합니다.  
  
### 사례 2   lpszSQL \= 테이블 이름  
 레코드 집합은 RFX\(레코드 필드 교환\)를 사용하여 레코드 집합 클래스의 `DoFieldExchange` 재정의에서 RFX 함수 호출에 제공된 열 이름으로부터 열 목록을 빌드합니다.  마법사를 사용하여 레코드 집합 클래스를 선언한 경우 사례 1과 같은 결과가 생깁니다\(마법사에서 지정한 것과 동일한 테이블 이름을 전달한 경우\).  마법사를 사용하여 클래스를 작성하지 않는 경우 SQL 문을 생성하려면 사례 2가 가장 간단합니다.  
  
 다음은 MFC 데이터베이스 응용 프로그램에서 레코드를 선택하는 SQL 문 생성 예제입니다.  프레임워크가 `GetDefaultSQL` 멤버 함수를 호출하면 이 함수는 `SECTION`이라는 테이블 이름을 반환합니다.  
  
```  
CString CEnrollSet::GetDefaultSQL()  
{  
    return "SECTION";  
}  
```  
  
 SQL **SELECT** 문의 열 이름을 구하기 위해 프레임워크는 `DoFieldExchange` 멤버 함수를 호출합니다.  
  
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
  
 완성된 SQL 문은 다음과 같습니다.  
  
```  
SELECT CourseID, InstructorID, RoomNo, Schedule, SectionNo   
    FROM SECTION  
```  
  
### 사례 3   lpszSQL \= SELECT\/FROM 문  
 RFX가 자동으로 열 목록을 생성하도록 하는 대신 사용자가 직접 열 목록을 지정합니다.  다음과 같은 경우 사용자가 직접 열 목록을 지정할 수 있습니다.  
  
-   **SELECT** 다음에 **DISTINCT** 키워드를 지정할 경우  
  
     열 목록은 `DoFieldExchange`에 나열되는 것과 동일한 순서로 열 이름 및 형식이 일치해야 합니다.  
  
-   RFX를 사용하여 열을 자동으로 바인딩하고 검색하는 대신 ODBC 함수 **::SQLGetData**를 사용하여 열 값을 직접 검색해야 하는 경우  
  
     예를 들면, 응용 프로그램을 배포한 후 해당 응용 프로그램의 사용자가 데이터베이스 테이블에 추가한 새 열을 허용하려는 경우가 있습니다.  이 추가 필드 데이터 멤버는 마법사를 사용하여 클래스를 선언할 때 인식되지 않았으므로 사용자가 직접 추가해야 합니다.  
  
     열 목록은 `DoFieldExchange`에 나열되는 것과 동일한 순서로 열 이름 및 형식이 일치해야 하며 직접 바인딩한 열 이름 앞에 나와야 합니다.  자세한 내용은 [레코드 집합: 데이터 열 동적 바인딩\(ODBC\)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)을 참조하십시오.  
  
-   **FROM** 절에서 여러 테이블을 지정하여 테이블을 조인해야 하는 경우  
  
     자세한 내용과 예제는 [레코드 집합: 조인 수행\(ODBC\)](../../data/odbc/recordset-performing-a-join-odbc.md)을 참조하십시오.  
  
### 사례 4   lpszSQL \= SELECT\/FROM과 WHERE 및\/또는 ORDER BY를 함께 사용  
 열 목록\(`DoFieldExchange`의 RFX 호출을 기준으로 함\), 테이블 목록, **WHERE** 및\/또는 **ORDER BY** 절의 내용 등 모든 사항을 사용자가 지정합니다.  이 방법으로 **WHERE** 및\/또는 **ORDER BY** 절을 지정하는 경우에는 **m\_strFilter** 및\/또는 `m_strSort`를 사용하지 않아야 합니다.  
  
### 사례 5   lpszSQL \= 저장 프로시저 호출  
 미리 정의된 쿼리\(예: Microsoft SQL Server 데이터베이스의 저장 프로시저\)를 호출하는 경우 `lpszSQL`에 전달되는 문자열에 **CALL** 문을 작성해야 합니다.  마법사에서는 미리 정의된 쿼리를 호출하기 위한 레코드 집합 클래스 선언을 지원하지 않습니다.  이는 미리 정의된 쿼리가 모두 레코드를 반환하는 것은 아니기 때문입니다.  
  
 미리 정의된 쿼리가 레코드를 반환하지 않는 경우 `CDatabase` 멤버 함수인 `ExecuteSQL`을 직접 사용해도 됩니다.  미리 정의된 쿼리가 레코드를 반환하는 경우에도 `DoFieldExchange`멤버 함수에 프로시저가 반환하는 모든 열에 대한 RFX 호출을 직접 작성해야 합니다.  RFX 호출은 미리 정의된 쿼리와 동일한 순서를 가져야 하며 동일한 형식을 반환해야 합니다.  자세한 내용은 [레코드 집합: 미리 정의된 쿼리에 대한 클래스 선언\(ODBC\)](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)을 참조하십시오.  
  
## 참고 항목  
 [SQL: SQL 및 C\+\+ 데이터 형식\(ODBC\)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)   
 [SQL: SQL 직접 호출\(ODBC\)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)