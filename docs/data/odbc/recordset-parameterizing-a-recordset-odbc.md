---
title: "레코드 집합: 레코드 집합 매개 변수화(ODBC) | Microsoft Docs"
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
  - "ODBC 레코드 집합, 매개 변수화"
  - "레코드 집합 매개 변수화"
  - "매개 변수 전달, 런타임에 쿼리에 적용"
  - "레코드 집합, 매개 변수화"
ms.assetid: 7d1dfeb6-5ee0-45e2-aacc-63bc52a465cd
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# 레코드 집합: 레코드 집합 매개 변수화(ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목은 MFC ODBC 클래스에 적용됩니다.  
  
 런타임에 최종 사용자에게 얻은 정보나 계산된 정보를 사용하여 레코드를 선택해야 하는 경우  레코드 집합 매개 변수를 사용하면 됩니다.  
  
 다음은 이 항목에서 설명하는 내용입니다.  
  
-   [매개 변수화된 레코드 집합의 목적](#_core_parameterized_recordsets)  
  
-   [레코드 집합을 매개 변수화하는 시기 및 이유](#_core_when_to_use_parameters)  
  
-   [레코드 집합 클래스에서 매개 변수 데이터 멤버를 선언하는 방법](#_core_parameterizing_your_recordset_class)  
  
-   [런타임에 매개 변수 정보를 레코드 집합 개체에 전달하는 방법](#_core_passing_parameter_values_at_run_time)  
  
##  <a name="_core_parameterized_recordsets"></a> 매개 변수가 있는 레코드 집합  
 매개 변수가 있는 레코드 집합을 사용하여 런타임에 매개 변수 정보를 전달할 수 있습니다.  이렇게 하면 다음과 같은 두 가지 효과를 얻을 수 있습니다.  
  
-   실행 속도가 빨라질 수 있습니다.  
  
-   사용자로부터 얻어야 하는 정보나 계산해야 하는 정보와 같이 디자인 타임에는 사용할 수 없는 정보를 기반으로 런타임에 쿼리를 만들 수 있습니다.  
  
 쿼리를 실행하기 위해 **Open**을 호출하면 레코드 집합은 매개 변수 정보를 사용하여 레코드 집합의 **SQL SELECT** 문을 완료합니다.  모든 레코드 집합을 매개 변수화할 수 있습니다.  
  
##  <a name="_core_when_to_use_parameters"></a> 매개 변수 사용 시기  
 매개 변수는 일반적으로 다음과 같이 사용됩니다.  
  
-   런타임 인수를 미리 정의된 쿼리로 전달합니다.  
  
     매개 변수를 저장 프로시저로 전달하려면 **Open**을 호출할 때 레코드 집합의 기본 SQL 문을 재정의하고 매개 변수 자리 표시자를 사용하여 완전한 사용자 지정 ODBC **CALL** 문을 지정해야 합니다.  자세한 내용은 클래스 라이브러리 참조의 [CRecordset::Open](../Topic/CRecordset::Open.md)과 [SQL: 레코드 집합의 SQL 문 사용자 지정\(ODBC\)](../../data/odbc/sql-customizing-your-recordset’s-sql-statement-odbc.md) 및 [레코드 집합: 미리 정의된 쿼리에 대한 클래스 선언\(ODBC\)](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)을 참조하십시오.  
  
-   서로 다른 매개 변수 정보를 사용하여 효율적으로 다시 쿼리를 여러 번 실행합니다.  
  
     예를 들어 최종 사용자가 학생 등록 데이터베이스에서 특정 학생에 대한 정보를 찾을 때마다 학생 이름이나 ID를 사용자가 입력한 매개 변수로 지정할 수 있습니다.  이렇게 하면 레코드 집합의 **Requery** 멤버 함수를 호출할 때 쿼리는 해당 학생의 레코드만을 선택합니다.  
  
     **m\_strFilter**에 저장되는 레코드 집합의 필터 문자열은 다음과 같습니다.  
  
    ```  
    "StudentID = ?"  
    ```  
  
     `strInputID` 변수에서 학생 ID를 가져오는 경우  매개 변수를 `strInputID`로 설정하면\(예: 학생 ID 100\) 변수 값은 필터 문자열에 "?"로 표시되는 매개 변수 자리 표시자에 바인딩됩니다.  
  
     매개 변수 값을 다음과 같이 할당합니다.  
  
    ```  
    strInputID = "100";  
    ...  
    m_strParam = strInputID;  
    ```  
  
     필터 문자열을 다음과 같은 방식으로 설정하지 않습니다.  
  
    ```  
    m_strFilter = "StudentID = 100";   // 100 is incorrectly quoted  
                                       // for some drivers  
    ```  
  
     필터 문자열에 대한 올바른 인용 부호 사용 방법은 [레코드 집합: 레코드 필터링\(ODBC\)](../../data/odbc/recordset-filtering-records-odbc.md)을 참조하십시오.  
  
     매개 변수 값은 레코드 집합에서 새 학생 ID를 다시 쿼리할 때마다 달라집니다.  
  
    > [!TIP]
    >  매개 변수를 사용하면 단순히 필터를 사용하는 것보다 더 효율적입니다.  매개 변수가 있는 레코드 집합의 경우 데이터베이스는 SQL **SELECT** 문을 한 번만 처리하면 되지만,  매개 변수 없이 필터링된 레코드 집합의 경우 새 필터 값을 사용하여 **Requery**할 때마다 **SELECT** 문을 처리해야 합니다.  
  
 필터에 대한 자세한 내용은 [레코드 집합: 레코드 필터링\(ODBC\)](../../data/odbc/recordset-filtering-records-odbc.md)을 참조하십시오.  
  
##  <a name="_core_parameterizing_your_recordset_class"></a> 레코드 집합 클래스 매개 변수화  
  
> [!NOTE]
>  이 단원은 대량 행 페치가 구현되지 않은 `CRecordset`에서 파생된 개체에 적용됩니다.  대량 행 페치를 사용하는 경우 매개 변수 구현 프로세스는 일반적인 경우와 유사합니다.  자세한 내용은 [레코드 집합: 대량 레코드 페치\(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)를 참조하십시오.  
  
 레코드 집합 클래스를 만들기 전에 필요한 매개 변수, 데이터 형식 및 레코드 집합에서 매개 변수를 사용하는 방법을 결정합니다.  
  
#### 레코드 집합 클래스를 매개 변수화하려면  
  
1.  **클래스 추가**에서 [MFC ODBC 소비자 마법사](../../mfc/reference/adding-an-mfc-odbc-consumer.md)를 실행하여 클래스를 만듭니다.  
  
2.  레코드 집합의 열에 대한 필드 데이터 멤버를 지정합니다.  
  
3.  마법사에서 프로젝트 파일에 클래스를 작성하고 나면 사용자가 직접 .h 파일에서 하나 이상의 매개 변수 데이터 멤버를 클래스 선언에 추가합니다.  그 결과를 보여주는 다음 예제는 "상급반에는 어떤 학생이 있습니까?" 같은 쿼리에 답하도록 디자인된 스냅숏 클래스의 일부분입니다.  
  
    ```  
    class CStudentSet : public CRecordset  
    {  
    // Field/Param Data  
        CString m_strFirstName;  
        CString m_strLastName;  
        CString m_strStudentID;  
        CString m_strGradYear;  
  
        CString m_strGradYrParam;  
    };  
    ```  
  
     마법사에서 만든 필드 데이터 멤버 다음에 매개 변수 데이터 멤버를 추가합니다.  규칙에 따라 "Param"을 각 사용자 정의 매개 변수 이름에 추가해야 합니다.  
  
4.  .cpp 파일에서 [DoFieldExchange](../Topic/CRecordset::DoFieldExchange.md) 멤버 함수 정의를 수정합니다.  클래스에 추가한 각 매개 변수 데이터 멤버에 대해 RFX 함수 호출을 추가합니다.  RFX 함수 작성에 대한 자세한 내용은 [레코드 필드 교환: RFX 작동 방식](../../data/odbc/record-field-exchange-how-rfx-works.md)을 참조하십시오.  단일 호출을 사용하여 해당 매개 변수에 대해 RFX 함수를 호출합니다.  
  
    ```  
    pFX->SetFieldType( CFieldExchange::param );  
    // RFX calls for parameter data members  
    ```  
  
5.  레코드 집합 클래스의 생성자에서 매개 변수 `m_nParams`의 개수를 늘립니다.  
  
     자세한 내용은 [레코드 필드 교환: 마법사 코드 사용](../../data/odbc/record-field-exchange-working-with-the-wizard-code.md)을 참조하십시오.  
  
6.  이 클래스의 레코드 집합 개체를 만드는 코드를 작성할 때 SQL 문 문자열에서 대체할 매개 변수가 있는 각 위치에 물음표\(?\)를 넣습니다.  
  
     런타임에 "?" 자리 표시자에는 전달되는 매개 변수 값이 순서대로 채워집니다.  [SetFieldType](../Topic/CFieldExchange::SetFieldType.md) 호출 다음에 설정된 첫째 매개 변수 데이터 멤버는 SQL 문자열의 첫째 "?"를, 둘째 매개 변수 데이터 멤버는 둘째 "?"를 대체하는 방식으로 처리됩니다.  
  
> [!NOTE]
>  이 경우 매개 변수 순서가 중요합니다. 즉, `DoFieldExchange` 함수에서 매개 변수에 대한 RFX 호출 순서와 SQL 문자열에 있는 매개 변수 자리 표시자의 순서가 일치해야 합니다.  
  
> [!TIP]
>  작업하는 문자열은 대개 클래스의 [m\_strFilter](../Topic/CRecordset::m_strFilter.md) 데이터 멤버에 대해 사용자 지정된 문자열\(있을 경우\)이지만 일부 ODBC 드라이버에서는 다른 SQL 절에서 매개 변수를 사용할 수 있습니다.  
  
##  <a name="_core_passing_parameter_values_at_run_time"></a> 런타임에 매개 변수 값 전달  
 **Open**\(새 레코드 집합 개체의 경우\) 또는 **Requery**\(기존 개체의 경우\)를 호출하기 전에 매개 변수 값을 지정해야 합니다.  
  
#### 런타임에 매개 변수 값을 레코드 집합 개체에 전달하려면  
  
1.  레코드 집합 개체를 생성합니다.  
  
2.  SQL 문 전체나 일부를 포함하는 **m\_strFilter** 등의 문자열을 준비합니다.  매개 변수 정보가 들어갈 위치에 "?" 자리 표시자를 넣습니다.  
  
3.  개체의 각 매개 변수 데이터 멤버에 런타임 매개 변수 값을 할당합니다.  
  
4.  **Open** 멤버 함수를 호출하거나 기존 레코드 집합의 경우 **Requery**를 호출합니다.  
  
 예를 들어 런타임에 얻은 정보를 사용하여 레코드 집합에 대한 필터 문자열을 지정한다고 가정합니다.  또한 앞에서 `CStudentSet` 클래스의 레코드 집합\(`rsStudent`\)을 만들었고 현재 학생에 대한 특정 정보를 얻기 위해 해당 레코드 집합을 다시 쿼리한다고 가정합니다.  
  
```  
// Set up a filter string with   
// parameter placeholders  
rsStudents.m_strFilter = "GradYear <= ?";  
  
// Obtain or calculate parameter values   
// to pass--simply assigned here   
CString strGradYear = GetCurrentAcademicYear( );  
  
// Assign the values to parameter data members  
rsStudents.m_strGradYrParam = strGradYear;  
  
// Run the query  
if( !rsStudents.Requery( ) )  
    return FALSE;  
```  
  
 레코드 집합에는 필터에 지정된 조건에 맞는 레코드를 가진 학생에 대한 레코드가 포함되며 이 필터는 런타임 매개 변수에서 생성되었습니다.  이 경우 레코드 집합에는 모든 상급반 학생에 대한 레코드가 포함됩니다.  
  
> [!NOTE]
>  필요한 경우 [SetParamNull](../Topic/CRecordset::SetParamNull.md)을 사용하여 매개 변수 데이터 멤버의 값을 Null로 설정할 수 있습니다.  마찬가지로 [IsFieldNull](../Topic/CRecordset::IsFieldNull.md)을 사용하여 매개 변수 데이터 멤버가 Null인지 여부를 확인할 수 있습니다.  
  
## 참고 항목  
 [레코드 집합\(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [레코드 집합: 레코드 추가, 업데이트 및 삭제\(ODBC\)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)   
 [레코드 집합: 레코드 집합의 레코드 선택 방법\(ODBC\)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)