---
title: "레코드 집합: 레코드 정렬(ODBC) | Microsoft Docs"
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
  - "ODBC 레코드 집합, 정렬"
  - "레코드 집합, 정렬"
  - "데이터 정렬, 레코드 집합 데이터"
ms.assetid: b40b152e-0a91-452e-be7b-e5bc27f744c7
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 레코드 집합: 레코드 정렬(ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목은 MFC ODBC 클래스에 적용됩니다.  
  
 이 항목에서는 레코드 집합을 정렬하는 방법에 대해 설명합니다.  정렬의 기준으로 사용할 하나 이상의 열을 지정하고 지정한 각 열에 대해 오름차순 또는 내림차순\(`ASC` 또는 **DESC**, 기본값은 `ASC`\)을 지정할 수 있습니다.  예를 들어, 열을 두 개 지정하는 경우 레코드는 명명된 첫째 열에서 먼저 정렬된 다음 명명된 둘째 열에서 정렬됩니다.  SQL **ORDER BY** 절은 정렬을 정의합니다.  프레임워크가 레코드 집합의 SQL 쿼리에 **ORDER BY** 절을 추가하면 이 절은 선택된 열을 정렬하는 기준을 제공합니다.  
  
 개체를 생성한 후 **Open** 멤버 함수를 호출하기 전 또는 **Open** 멤버 함수가 호출된 기존 레코드 집합 개체에 대해 **Requery** 멤버 함수를 호출하기 전에 레코드 집합 정렬 순서를 설정해야 합니다.  
  
#### 레코드 집합 개체에 대한 정렬 순서를 지정하려면  
  
1.  새 레코드 집합 개체를 생성하거나 기존 개체에 대한 **Requery** 호출을 준비합니다.  
  
2.  해당 개체의 [m\_strSort](../Topic/CRecordset::m_strSort.md) 데이터 멤버 값을 설정합니다.  
  
     정렬은 null로 끝나는 문자열입니다.  정렬은 **ORDER BY** 절의 내용은 포함하지만 키워드 **ORDER BY**는 포함하지 않습니다.  예를 들어 다음과 같이 사용할 수 있습니다.  
  
    ```  
    recordset.m_strSort = "LastName DESC, FirstName DESC";  
    ```  
  
     not  
  
    ```  
    recordset.m_strSort = "ORDER BY LastName DESC, FirstName DESC";  
    ```  
  
3.  필터, 잠금 모드, 매개 변수 등 필요한 다른 옵션을 설정합니다.  
  
4.  새 개체에 대해 **Open**을 호출하거나 기존 개체에 대해 **Requery**를 호출합니다.  
  
 지정한 대로 선택된 레코드가 정렬됩니다.  예를 들어 학생 레코드 집합을 먼저 성을 기준으로, 다음은 이름을 기준으로 내림차순으로 정렬하려면 다음과 같이 작성합니다.  
  
```  
// Construct the recordset  
CStudentSet rsStudent( NULL );  
// Set the sort  
rsStudent.m_strSort = "LastName DESC, FirstName DESC";  
// Run the query with the sort in place  
rsStudent.Open( );  
```  
  
 레코드 집합에는 먼저 성을 기준으로, 다음은 이름을 기준으로 내림차순\(Z에서 A까지\)으로 정렬된 모든 학생 레코드가 포함됩니다.  
  
> [!NOTE]
>  SQL 문자열을 **Open**에 전달하여 레코드 집합의 기본 SQL 문자열을 재정의할 경우 사용자 지정 문자열에 **ORDER BY** 절이 있으면 정렬을 설정하지 않아야 합니다.  
  
## 참고 항목  
 [레코드 집합\(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [레코드 집합: 레코드 집합 매개 변수화\(ODBC\)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)   
 [레코드 집합: 레코드 필터링\(ODBC\)](../../data/odbc/recordset-filtering-records-odbc.md)