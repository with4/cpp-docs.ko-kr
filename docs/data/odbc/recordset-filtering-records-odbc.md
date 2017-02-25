---
title: "레코드 집합: 레코드 필터링(ODBC) | Microsoft Docs"
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
  - "데이터[MFC], 필터링"
  - "레코드 집합 필터링"
  - "필터[C++], 레코드 집합 개체"
  - "ODBC 레코드 집합[C++], 레코드 필터링"
  - "레코드 집합[C++], 필터링"
ms.assetid: 5c075f37-c837-464d-90c1-d028a9d1c175
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 레코드 집합: 레코드 필터링(ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목은 MFC ODBC 클래스에 적용됩니다.  
  
 이 항목에서는 사용할 수 있는 레코드의 특정 하위 집합만을 선택하도록 레코드 집합을 필터링하는 방법에 대해 설명합니다.  예를 들어 MATH101과 같은 특정 과목에 대한 학급만을 선택할 수도 있습니다.  필터는 SQL **WHERE** 절의 내용에 의해 정의되는 검색 조건입니다.  프레임워크에서 레코드 집합의 SQL 문에 필터를 추가하려면 **WHERE** 절은 SQL 문의 선택 범위를 제한합니다.  
  
 개체를 생성한 후 **Open** 멤버 함수를 호출하기 전 또는 **Open** 멤버 함수가 호출된 기존 레코드 집합 개체에 대해 **Requery** 멤버 함수를 호출하기 전에 레코드 집합 개체에 필터를 설정해야 합니다.  
  
#### 레코드 집합 개체에 필터를 지정하려면  
  
1.  새 레코드 집합 개체를 생성하거나 기존 개체에 대해 **Requery** 함수를 호출할 준비를 합니다.  
  
2.  해당 개체의 [m\_strFilter](../Topic/CRecordset::m_strFilter.md) 데이터 멤버 값을 설정합니다.  
  
     필터는 SQL **WHERE** 절의 내용이 들어 있지만 **WHERE** 키워드가 없는 null로 끝나는 문자열입니다.  예를 들어 다음과 같이 사용할 수 있습니다.  
  
    ```  
    m_pSet->m_strFilter = "CourseID = 'MATH101'";  
    ```  
  
     not  
  
    ```  
    m_pSet->m_strFilter = "WHERE CourseID = 'MATH101'";  
    ```  
  
    > [!NOTE]
    >  위의 예에서 리터럴 문자열 "MATH101"은 작은따옴표로 묶여 있습니다.  ODBC SQL 사양에서는 작은따옴표를 사용하여 문자열 리터럴을 나타냅니다.  이러한 상황에서 DBMS에 필요한 따옴표 사용 요구 사항에 대해서는 ODBC 드라이버 설명서를 확인하십시오.  이 항목의 끝 부분에서 이 구문을 더 자세히 설명합니다.  
  
3.  정렬 순서, 잠금 모드, 매개 변수 등 필요한 다른 옵션을 설정합니다.  매개 변수를 지정하면 특히 유용합니다.  필터를 매개 변수화하는 내용은 [레코드 집합: 레코드 집합 매개 변수화\(ODBC\)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)를 참조하십시오.  
  
4.  새 개체에 대해 **Open**을 호출하거나 이전에 연 개체에 대해 **Requery**를 호출합니다.  
  
> [!TIP]
>  필터에서 매개 변수를 사용하는 것이 레코드를 검색하는 데 가장 효율적입니다.  
  
> [!TIP]
>  레코드 집합 필터는 테이블을 [조인](../../data/odbc/recordset-performing-a-join-odbc.md)하거나 런타임에 가져오거나 계산된 정보를 기준으로 [매개 변수](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)를 사용하는 데 유용합니다.  
  
 레코드 집합에서는 지정된 검색 조건에 맞는 레코드만 선택됩니다.  예를 들어, `strCourseID` 변수가 현재 "MATH101"로 설정된 경우 앞에서 설명한 과목 필터를 지정하려면 아래와 같이 작성합니다.  
  
```  
// Using the recordset pointed to by m_pSet  
  
// Set the filter  
m_pSet->m_strFilter = "CourseID = " + strCourseID;   
  
// Run the query with the filter in place  
if ( m_pSet->Open( CRecordset::snapshot, NULL, CRecordset::readOnly ) )  
  
// Use the recordset  
```  
  
 레코드 집합에는 MATH101에 대한 모든 학급의 레코드가 포함됩니다.  
  
 위 예제에서 문자열 변수를 사용하여 필터 문자열이 설정된 방법에 유의하십시오.  일반적으로 위와 같이 사용되지만  과목 ID에 리터럴 값 100을 지정한 경우  이 리터럴 값을 사용하여 필터 문자열을 설정하려면 다음과 같이 코드를 작성해야 합니다.  
  
```  
m_strFilter = "StudentID = '100'";   // correct  
```  
  
 작은따옴표를 적절하게 사용해야 합니다. 필터 문자열을 직접 설정하는 경우에는 아래와 같이 할 수 **없습니다**.  
  
```  
m_strFilter = "StudentID = 100";   // incorrect for some drivers  
```  
  
 위에 나온 인용 부호는 ODBC 사양을 따르지만 일부 DBMS에서는 다른 인용 문자를 사용합니다.  자세한 내용은 [SQL: 레코드 집합의 SQL 문 사용자 지정\(ODBC\)](../../data/odbc/sql-customizing-your-recordset’s-sql-statement-odbc.md)을 참조하십시오.  
  
> [!NOTE]
>  SQL 문자열을 **Open**에 전달하여 레코드 집합의 기본 SQL 문자열을 재정의할 경우 사용자 지정 문자열에 **WHERE** 절이 있으면 필터를 설정하지 않아야 합니다.  기본 SQL을 재정의하는 데 대한 자세한 내용은 [SQL: 레코드 집합의 SQL 문 사용자 지정\(ODBC\)](../../data/odbc/sql-customizing-your-recordset’s-sql-statement-odbc.md)을 참조하십시오.  
  
## 참고 항목  
 [레코드 집합\(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [레코드 집합: 레코드 정렬\(ODBC\)](../../data/odbc/recordset-sorting-records-odbc.md)   
 [레코드 집합: 레코드 집합의 레코드 선택 방법\(ODBC\)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)   
 [레코드 집합: 레코드 집합의 레코드 업데이트 방법\(ODBC\)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)   
 [레코드 집합: 레코드 잠금\(ODBC\)](../../data/odbc/recordset-locking-records-odbc.md)