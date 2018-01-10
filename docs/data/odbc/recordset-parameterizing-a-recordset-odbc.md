---
title: "레코드 집합: 레코드 집합 (ODBC)를 매개 변수화 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- parameterizing recordsets
- ODBC recordsets, parameterizing
- recordsets, parameterizing
- passing parameters, to queries at runtime
ms.assetid: 7d1dfeb6-5ee0-45e2-aacc-63bc52a465cd
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 38b17950a7aaf89cc041c4933768bf6b2da0c9b0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="recordset-parameterizing-a-recordset-odbc"></a>레코드 집합: 레코드 집합 매개 변수화(ODBC)
MFC ODBC 클래스에이 항목에 적용 됩니다.  
  
 경우에 따라 하려는 런타임 시 레코드를 선택할 수 계산 하거나 최종 사용자 로부터 얻은 정보를 사용 하 여 합니다. 레코드 집합 매개 변수를 통해 해당 목표를 달성할 수 있습니다.  
  
 이 항목에 설명 합니다.  
  
-   [매개 변수가 있는 레코드 집합의 목적은](#_core_parameterized_recordsets)합니다.  
  
-   [레코드 집합 매개 변수화 하는 시기 및 이유](#_core_when_to_use_parameters)합니다.  
  
-   [레코드 집합 클래스의 데이터 멤버의 매개 변수를 선언 하는 방법](#_core_parameterizing_your_recordset_class)합니다.  
  
-   [런타임 시 recordset 개체에 매개 변수 정보를 전달 하는 방법을](#_core_passing_parameter_values_at_run_time)합니다.  
  
##  <a name="_core_parameterized_recordsets"></a>매개 변수가 있는 레코드 집합  
 매개 변수가 있는 레코드 집합 사용 하면 실행 시 매개 변수 정보를 전달할 수 있습니다. 이 두 가지 중요 한 효과가 있습니다.  
  
-   실행 속도가 빨라질 발생할 수 있습니다.  
  
-   정보 사용자 로부터 얻은 되었다거나 런타임 시 계산 되는 등 디자인 타임에 게 사용할 수 없는 정보에 따라 실행 시 쿼리를 작성할 수 있습니다.  
  
 호출 하는 경우 **열려** 쿼리를 실행 하는 레코드 집합을 사용 하 여 매개 변수 정보 완료 해당 **SQL SELECT** 문. 모든 레코드 집합 매개 변수화 할 수 있습니다.  
  
##  <a name="_core_when_to_use_parameters"></a>매개 변수를 사용 하는 경우  
 매개 변수의 일반적인 용도 다음과 같습니다.  
  
-   미리 정의 된 쿼리를 실행 시간 인수를 전달 합니다.  
  
     저장된 프로시저에 매개 변수를 전달 하려면 완전 한 사용자 지정 ODBC 지정 해야 **호출** 문-매개 변수 자리 표시자-호출 하는 경우 **열려**, 레코드 집합의 기본 SQL 문을 재정의 합니다. 자세한 내용은 참조 [crecordset:: Open](../../mfc/reference/crecordset-class.md#open) 에 *클래스 라이브러리 참조* 및 [SQL: 사용자 지정 레코드 집합의 SQL 문 (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md) 및 [ 레코드 집합: 미리 정의 된 쿼리 (ODBC)에 대 한 클래스 선언](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)합니다.  

  
-   다른 매개 변수 정보로 다양 한 재쿼리를 효율적으로 수행 합니다.  
  
     예를 들어 최종 사용자에 게 특정 학생에 학생 등록 데이터베이스에 대 한 정보를 조회 때마다 지정할 수 있습니다 학생의 이름 또는 ID가 사용자에 게 서 얻은 매개 변수로 합니다. 그런 다음 호출 하는 경우 레코드 집합의 **Requery** 해당 학생의 레코드만 선택 하는 멤버 함수를 쿼리 합니다.  
  
     에 저장 된 레코드 집합의 필터 문자열 **m_strFilter**, 아래와 같습니다.  
  
    ```  
    "StudentID = ?"  
    ```  
  
     변수에서 학생 ID를 가져오는 `strInputID`합니다. 매개 변수 설정 하면 `strInputID` 나타내는 매개 변수 자리 표시자에 바인딩된 변수 값 (예: 학생 ID가 100)는 "?"는 필터 문자열의 합니다.  
  
     매개 변수 값을 다음과 같이 지정 합니다.  
  
    ```  
    strInputID = "100";  
    ...  
    m_strParam = strInputID;  
    ```  
  
     이러한 방식으로 한 필터 문자열을 설정 하지 않을 수도 있습니다.  
  
    ```  
    m_strFilter = "StudentID = 100";   // 100 is incorrectly quoted  
                                       // for some drivers  
    ```  
  
     필터 문자열에 대 한 따옴표를 잘못 사용 하는 방법의 논의 알려면 [레코드 집합: 레코드 필터링 (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)합니다.  
  
     매개 변수 값이 다른 새 학생 ID에 대 한 레코드 집합 다시 쿼리할 때마다  
  
    > [!TIP]
    >  매개 변수를 사용 하면 단순히 필터 보다 더 효율적입니다. 매개 변수가 있는 레코드 집합에 대 한 데이터베이스는 처리 하면 SQL **선택** 문을 한 번만 합니다. 매개 변수가 없을 경우 필터링 된 레코드 집합에 대 한는 **선택** 문을 처리 해야 할 때마다 **Requery** 새 필터 값으로.  
  
 필터에 대 한 자세한 내용은 참조 [레코드 집합: 레코드 필터링 (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)합니다.  
  
##  <a name="_core_parameterizing_your_recordset_class"></a>레코드 집합 클래스를 매개 변수화  
  
> [!NOTE]
>  이 섹션에서 파생 된 개체에 적용 됩니다. `CRecordset` 에서 대량 행 페치 구현 되지 않았습니다. 대량 행 페치를 구현 하는 매개 변수를 사용 하는 경우 비슷한 프로세스가입니다. 자세한 내용은 참조 [레코드 집합: 레코드 페치 대량 (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)합니다.  
  
 레코드 집합 클래스를 만들기 전에 필요한 매개 변수, 데이터 형식으로 이란, 및 레코드 집합 사용 하 여 방법을 결정 합니다.  
  
#### <a name="to-parameterize-a-recordset-class"></a>레코드 집합 클래스를 매개 변수화 하려면  
  
1.  실행 된 [MFC ODBC 소비자 마법사](../../mfc/reference/adding-an-mfc-odbc-consumer.md) 에서 **클래스 추가** 여 클래스를 만듭니다.  
  
2.  레코드 집합의 열에 대 한 필드 데이터 멤버를 지정 합니다.  
  
3.  프로젝트의 파일에 클래스를 작성 하는 마법사를 후.h 파일을 이동 하 고 수동으로 클래스 선언에 하나 이상의 매개 변수 데이터 멤버를 추가 합니다. 추가 다음 예제와 유사할 수, 스냅숏 클래스의 일부 하도록 설계 된 쿼리에 응답 "에 어떤 학생이 상급?"  
  
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
  
     마법사에서 생성 된 필드 데이터 멤버 뒤 매개 변수 데이터 멤버를 추가 합니다. 규칙에 따라 각 사용자 정의 매개 변수 이름에 "Param" 이라는 단어를 추가 하는 것입니다.  
  
4.  수정 된 [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) .cpp 파일에서 멤버 함수 정의 합니다. 클래스에 추가한 각 매개 변수 데이터 멤버에 대해 RFX 함수 호출을 추가 합니다. RFX 함수 작성 하는 방법에 대 한 정보를 참조 하십시오. [레코드 필드 교환: RFX 작동 방식](../../data/odbc/record-field-exchange-how-rfx-works.md)합니다. 한 번 호출을 사용 하 여 매개 변수에 대해 RFX 호출 앞에 야 합니다.  
  
    ```  
    pFX->SetFieldType( CFieldExchange::param );  
    // RFX calls for parameter data members  
    ```  
  
5.  레코드 집합 클래스의 생성자에 매개 변수를의 횟수를 증가 `m_nParams`합니다.  
  
     자세한 내용은 참조 [레코드 필드 교환: 마법사 코드 사용](../../data/odbc/record-field-exchange-working-with-the-wizard-code.md)합니다.  
  
6.  이 클래스의 레코드 집합 개체를 만드는 코드를 작성 하는 경우는 "?" SQL 문 문자열 대체 되어야 하는 매개 변수는 여기서 각 위치에서 (물음표) 기호입니다.  
  
     런타임 시 "?" 자리 표시자 가득 차면 순서로, 매개 변수 값으로 전달 합니다. 후 설정 된 첫 번째 매개 변수 데이터 멤버는 [SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype) 호출할 첫 번째 바뀝니다 "?"에 SQL 문자열의 두 번째 매개 변수 데이터 멤버를 대체 두 번째"?" 등입니다.  
  
> [!NOTE]
>  매개 변수 순서는 중요: RFX의 순서에 대 한 매개 변수에 대 한 호출 프로그램 `DoFieldExchange` 함수에는 SQL 문자열의 매개 변수 자리 표시자의 순서와 일치 해야 합니다.  
  
> [!TIP]

>  작업할 가능성이 가장 높은 문자열은 지정한 문자열 (있는 경우)는 클래스에 대 한 [m_strFilter](../../mfc/reference/crecordset-class.md#m_strfilter) 데이터 멤버 이지만 일부 ODBC 드라이버 다른 SQL 절에서 매개 변수를 사용할 수 있습니다.  
  
##  <a name="_core_passing_parameter_values_at_run_time"></a>실행 시 매개 변수 값 전달  
 호출 하기 전에 매개 변수 값을 지정 해야 **열려** (새 recordset 개체)에 대 한 또는 **Requery** (에 대 한 기존).  
  
#### <a name="to-pass-parameter-values-to-a-recordset-object-at-run-time"></a>런타임 시 recordset 개체에 매개 변수 값을 전달 하려면  
  
1.  레코드 집합 개체를 생성 합니다.  
  
2.  와 같은 문자열 또는 문자열을 준비는 **m_strFilter** SQL 문 또는 일부를 포함 하는 문자열입니다. 배치 "?" 자리 표시자 매개 변수 정보를 이동 하입니다.  
  
3.  개체의 각 매개 변수 데이터 멤버에는 런타임에 매개 변수 값을 할당 합니다.  
  
4.  호출 된 **열려** 멤버 함수 (또는 **Requery**, 기존 레코드 집합에 대 한).  
  
 예를 들어 런타임 시 얻은 정보를 사용 하 여 레코드 집합에 대 한 필터 문자열을 지정 한다고 가정 합니다. 클래스의 레코드 집합을 생성 한 것으로 가정 `CStudentSet` 앞-호출 `rsStudents` -및 특정 종류의 학생 정보에 대해 다시 쿼리 합니다.  
  
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
  
 레코드 집합 레코드가 런타임 매개 변수에서 생성 된 필터에 의해 지정 된 조건을 충족 학생에 대 한 레코드를 포함 합니다. 이 경우 레코드 집합 모든 수석 학생에 대 한 레코드를 포함합니다.  
  
> [!NOTE]
>  필요한 경우 매개 변수 데이터 멤버의 값을 Null로 설정할 수 있습니다를 사용 하 여 [SetParamNull](../../mfc/reference/crecordset-class.md#setparamnull)합니다. Null 매개 변수 데이터 멤버 인지 마찬가지로 확인할 수 있습니다를 사용 하 여 [IsFieldNull](../../mfc/reference/crecordset-class.md#isfieldnull)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [레코드 집합 (ODBC)](../../data/odbc/recordset-odbc.md)   
 [레코드 집합: 추가, 업데이트 및 삭제할 레코드 (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)   
 [레코드 집합: 레코드 집합의 레코드 선택 방법(ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)