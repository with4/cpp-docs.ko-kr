---
title: "레코드 집합: 레코드 정렬 (ODBC) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- sorting data, recordset data
- ODBC recordsets, sorting
- recordsets, sorting
ms.assetid: b40b152e-0a91-452e-be7b-e5bc27f744c7
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 846b3cfd4d5abe6d0eb76cfb12840f094564c926
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="recordset-sorting-records-odbc"></a>레코드 집합: 레코드 정렬(ODBC)
MFC ODBC 클래스에이 항목에 적용 됩니다.  
  
 이 항목에서는 레코드 집합을 정렬 하는 방법에 설명 합니다. 에 정렬 기준으로 사용할 하나 이상의 열을 지정할 수 있으며 오름차순 또는 내림차순을 지정할 수 있습니다 (`ASC` 또는 **DESC**; `ASC` 기본값임) 지정 된 각 열에 대 한 합니다. 예를 들어 두 개의 열을 지정 하면 레코드 차례로 정렬 됩니다 먼저 명명 된 첫 번째 열에서 명명 된 두 번째 열에서 합니다. SQL **ORDER BY** 정렬 절을 정의 합니다. 프레임 워크가 추가 되는 경우는 **ORDER BY** 절을 레코드 집합의 SQL 쿼리 절 컨트롤 선택 항목의 순서 지정 합니다.  
  
 하지만 호출 하기 전에 개체를 생성 한 후 레코드 집합의 정렬 순서를 설정 해야 해당 **열려** 멤버 함수 (호출 하기 전에 또는 **Requery** 기존 레코드 집합 개체에 대 한 멤버 함수 해당 **열려** 멤버 함수가 이전에 호출 되었습니다).  
  
#### <a name="to-specify-a-sort-order-for-a-recordset-object"></a>레코드 집합 개체에 대 한 정렬 순서를 지정 하려면  
  
1.  새 레코드 집합 개체를 생성 합니다 (호출을 준비 또는 **Requery** 기존의).  
  
2.  개체의 값을 설정 [m_strSort](../../mfc/reference/crecordset-class.md#m_strsort) 데이터 멤버입니다.  
  
     정렬은 null로 끝나는 문자열입니다. 내용을 포함 된 **ORDER BY** 절 하지만 키워드가 아니라 **ORDER BY**합니다. 예를 들어 사용 합니다.  
  
    ```  
    recordset.m_strSort = "LastName DESC, FirstName DESC";  
    ```  
  
     not  
  
    ```  
    recordset.m_strSort = "ORDER BY LastName DESC, FirstName DESC";  
    ```  
  
3.  필터, 잠금 모드 또는 매개 변수 같은 사용자가 필요한 다른 옵션을 설정 합니다.  
  
4.  호출 **열려** 새 개체에 대 한 (또는 **Requery** 기존 개체에 대 한).  
  
 선택 된 레코드 상대적으로 정렬 지정 된 대로 합니다. 예를 들어 내림차순으로 성, 학생 레코드 집합을 정렬 하려면 다음을 수행 합니다.  
  
```  
// Construct the recordset  
CStudentSet rsStudent( NULL );  
// Set the sort  
rsStudent.m_strSort = "LastName DESC, FirstName DESC";  
// Run the query with the sort in place  
rsStudent.Open( );  
```  
  
 레코드 집합 모든 내림차순 정렬 (내림차순) 성,으로 다음 이름으로, 학생 레코드를 포함 합니다.  
  
> [!NOTE]
>  사용자 고유의 SQL 문자열을 전달 하 여 레코드 집합의 기본 SQL 문자열을 재정의 하도록 선택 **열려**, 사용자 지정 문자열에 있는 경우 정렬 하는 설정 하지 않으면는 **ORDER BY** 절.  
  
## <a name="see-also"></a>참고 항목  
 [레코드 집합 (ODBC)](../../data/odbc/recordset-odbc.md)   
 [레코드 집합: 레코드 집합 (ODBC)를 매개 변수화](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)   
 [레코드 집합: 레코드 필터링(ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)