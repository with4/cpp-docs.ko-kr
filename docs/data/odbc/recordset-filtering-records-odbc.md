---
title: '레코드 집합: 레코드 필터링 (ODBC) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- data [MFC], filtering
- recordsets [C++], filtering
- filtering recordsets
- ODBC recordsets [C++], filtering records
- filters [C++], recordset object
ms.assetid: 5c075f37-c837-464d-90c1-d028a9d1c175
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b6d6e8b41e67c9f33d643a2f64c7bdf2d2251eff
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="recordset-filtering-records-odbc"></a>레코드 집합: 레코드 필터링(ODBC)
MFC ODBC 클래스에이 항목에 적용 됩니다.  
  
 이 항목에서는 레코드 집합을 필터링 하는 사용할 수 있는 레코드의 특정 하위 집합만 선택 하는 방법에 설명 합니다. 예를 들어 다음 MATH101 등의 특정 과정에 대 한 클래스 부분에만 선택 하는 것이 좋습니다. 필터는 SQL의 내용에 의해 정의 된 검색 조건을 **여기서** 절. 프레임 워크가 레코드 집합의 SQL 문에 추가 **여기서** 절 선택 범위를 제한 합니다.  
  
 하지만 호출 하기 전에 개체를 생성 한 후에 레코드 집합 개체의 필터를 설정 해야 해당 **열려** 멤버 함수 (또는 호출 하기 전에 **Requery** 기존 레코드 집합에 대 한 멤버 함수 개체의 **열려** 멤버 함수가 이전에 호출 되었습니다).  
  
#### <a name="to-specify-a-filter-for-a-recordset-object"></a>레코드 집합 개체에 대 한 필터를 지정 하려면  
  
1.  새 레코드 집합 개체를 생성 합니다 (호출을 준비 또는 **Requery** 기존 개체에 대 한).  
  
2.  개체의 값을 설정 [m_strFilter](../../mfc/reference/crecordset-class.md#m_strfilter) 데이터 멤버입니다.  
  
     필터는 SQL의 내용이 포함 된 null로 끝나는 문자열로 **여기서** 절 하지만 키워드가 아니라 **여기서**합니다. 예를 들어 사용 합니다.  
  
    ```  
    m_pSet->m_strFilter = "CourseID = 'MATH101'";  
    ```  
  
     not  
  
    ```  
    m_pSet->m_strFilter = "WHERE CourseID = 'MATH101'";  
    ```  
  
    > [!NOTE]
    >  리터럴 문자열 "MATH101" 위의 단일 인용 부호로 표시 됩니다. ODBC SQL 사양에 작은따옴표는 문자열 리터럴을 표시 하는 데 사용 됩니다. 이 상황에서 DBMS의 따옴표 요구 사항에 대 한 ODBC 드라이버 설명서를 확인 합니다. 이 구문은 설명 추가이 항목의 끝 근처 합니다.  
  
3.  정렬 순서, 잠금 모드 또는 매개 변수 같은 사용자가 필요한 다른 옵션을 설정 합니다. 매개 변수를 지정 하는 것은 특히 유용 합니다. 필터를 매개 변수화 하는 방법에 대 한 정보를 참조 하십시오. [레코드 집합: 레코드 집합 (ODBC)를 매개 변수화](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)합니다.  
  
4.  호출 **열려** 새 개체에 대 한 (또는 **Requery** 이전에 열린된 개체에 대 한).  
  
> [!TIP]
>  필터에 매개 변수를 사용 하는 잠재적으로 레코드를 검색 하기 위한 가장 효율적인 방법을 합니다.  
  
> [!TIP]
>  레코드 집합 필터는 데 유용 [조인](../../data/odbc/recordset-performing-a-join-odbc.md) 테이블 및 사용에 대 한 [매개 변수](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) 가져오거나 런타임 시 계산 된 정보에 기반 합니다.  
  
 지정한 검색 조건에 일치 하는 레코드만 일부 레코드를 선택 합니다. 위에 설명 된 과정 필터를 지정 (변수 가정 `strCourseID` 현재, 예를 들어, "MATH101"로 설정)에서 다음을 수행 합니다.  
  
```  
// Using the recordset pointed to by m_pSet  
  
// Set the filter  
m_pSet->m_strFilter = "CourseID = " + strCourseID;   
  
// Run the query with the filter in place  
if ( m_pSet->Open( CRecordset::snapshot, NULL, CRecordset::readOnly ) )  
  
// Use the recordset  
```  
  
 레코드 집합 MATH101에 대 한 모든 클래스 섹션에 대 한 레코드를 포함합니다.  
  
 문자열 변수를 사용 하 여 위의 예제에서 필터 문자열을 설정 하는 방법을 살펴보십시오. 일반적인 사용법입니다. 과목 ID에 대 한 리터럴 값 100을 지정 한다고 가정 하지만 다음 코드에는 리터럴 값을 사용 하 여 올바르게 필터 문자열을 설정 하는 방법을 보여 줍니다.  
  
```  
m_strFilter = "StudentID = '100'";   // correct  
```  
  
 참고; 작은따옴표 문자 사용 필터 문자열을 직접 설정 하는 경우에 **하지**:  
  
```  
m_strFilter = "StudentID = 100";   // incorrect for some drivers  
```  
  
 인용 부호 위에 표시 된 ODBC 사양에 하지만 일부 Dbms 다른 인용 문자 필요할 수 있습니다. 자세한 내용은 참조 [SQL: 사용자 지정 레코드 집합의 SQL 문 (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md)합니다.  
  
> [!NOTE]
>  사용자 고유의 SQL 문자열을 전달 하 여 레코드 집합의 기본 SQL 문자열을 재정의 하도록 선택 **열려**, 사용자 지정 문자열에 있으면 필터를 설정 하지 않아야는 **여기서** 절. 기본 SQL를 재정의 하는 방법에 대 한 자세한 내용은 참조 [SQL: 사용자 지정 레코드 집합의 SQL 문 (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [레코드 집합 (ODBC)](../../data/odbc/recordset-odbc.md)   
 [레코드 집합: 레코드 정렬 (ODBC)](../../data/odbc/recordset-sorting-records-odbc.md)   
 [레코드 집합: 레코드 집합 선택 레코드 방법 (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)   
 [레코드 집합: 레코드 집합 업데이트 레코드 방법 (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)   
 [레코드 집합: 레코드 잠금(ODBC)](../../data/odbc/recordset-locking-records-odbc.md)