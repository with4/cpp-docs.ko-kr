---
title: "레코드 집합: 레코드 집합 다시 쿼리(ODBC) | Microsoft Docs"
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
  - "ODBC 레코드 집합, 다시 쿼리"
  - "레코드 집합, 다시 쿼리"
  - "레코드 집합 새로 고침"
  - "Requery 메서드"
  - "레코드 집합 다시 쿼리"
ms.assetid: 4ebc3b5b-5b91-4f51-a967-245223c6b8e1
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 레코드 집합: 레코드 집합 다시 쿼리(ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목은 MFC ODBC 클래스에 적용됩니다.  
  
 이 항목에서는 레코드 집합 개체를 사용하여 데이터베이스에서 자체를 다시 쿼리, 즉 새로 고치는 방법 및 [Requery](../Topic/CRecordset::Requery.md) 멤버 함수를 사용하여 이 작업을 수행하는 시기에 대해 설명합니다.  
  
 레코드 집합을 다시 쿼리하는 주요 이유는 다음과 같습니다.  
  
-   자신 또는 다른 사용자가 추가한 레코드 및 다른 사용자가 삭제한 레코드를 반영하도록 레코드 집합을 업데이트합니다. 자신이 삭제한 레코드는 레코드 집합에 이미 반영되어 있습니다.  
  
-   매개 변수 값이 변경되면 레코드 집합을 새로 고칩니다.  
  
##  <a name="_core_bringing_the_recordset_up_to_date"></a> 레코드 집합 업데이트  
 경우에 따라서는 레코드 집합 개체를 다시 쿼리하여 업데이트해야 할 수도 있습니다.  다중 사용자 데이터베이스 환경에서는 레코드 집합을 사용하는 동안 다른 사용자가 데이터를 변경할 수 있습니다.  다른 사용자가 변경한 내용을 레코드 집합에 반영하는 시기와 자신의 변경 내용이 다른 사용자의 레코드 집합에 반영되는 시기에 대한 자세한 내용은 [레코드 집합: 레코드 집합의 레코드 업데이트 방법\(ODBC\)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md) 및 [다이너셋](../../data/odbc/dynaset.md)을 참조하십시오.  
  
##  <a name="_core_requerying_based_on_new_parameters"></a> 새 매개 변수에 기반하여 다시 쿼리하기  
 [Requery](../Topic/CRecordset::Requery.md)는 변경된 매개 변수 값에 기반하여 새 레코드 집합을 선택하는 경우에도 자주 사용되는 만큼 중요한 역할을 합니다.  
  
> [!TIP]
>  쿼리 속도는 **Open**을 다시 호출하는 것보다 매개 변수 값을 변경하여 **Requery**를 호출하는 경우가 훨씬 빠릅니다.  
  
##  <a name="_core_requerying_dynasets_vs.._snapshots"></a> Requerying Dynasets vs. Snapshots  
 다이너셋은 동적으로 업데이트되는 데이터가 포함된 레코드 집합을 제공하는 데 사용되므로 다른 사용자가 추가한 내용을 반영하려면 다이너셋을 자주 다시 쿼리해야 합니다.  반면에 스냅숏은 보고서를 작성하고 총계를 계산하는 등의 작업을 수행할 때 스냅숏의 자주 변경되지 않는 내용을 안전하게 사용할 수 있기 때문에 유용합니다.  그러나 스냅숏을 다시 쿼리해야 할 때도 있습니다.  다중 사용자 환경에서 다른 사용자가 데이터베이스를 변경하면 스냅숏 데이터와 해당 데이터베이스가 동기화되지 않을 수도 있습니다.  
  
#### 레코드 집합 개체를 다시 쿼리하려면  
  
1.  개체의 [Requery](../Topic/CRecordset::Requery.md) 멤버 함수를 호출합니다.  
  
 또는 원래 레코드 집합을 닫고 다시 열수도 있습니다.  두 경우 모두에서 새 레코드 집합은 데이터 소스의 현재 상태를 나타냅니다.  
  
 예제는 [레코드 뷰: 두 번째 레코드 집합에서 목록 상자 채우기](../../data/filling-a-list-box-from-a-second-recordset-mfc-data-access.md)를 참조하십시오.  
  
> [!TIP]
>  **Requery** 성능을 최적화하려면 레코드 집합의 [필터](../../data/odbc/recordset-filtering-records-odbc.md) 또는 [정렬](../../data/odbc/recordset-sorting-records-odbc.md)을 변경하지 마십시오.  **Requery**를 호출하기 전에 매개 변수 값만을 변경하십시오.  
  
 **Requery** 호출에 실패한 경우 다시 호출하거나 응용 프로그램을 종료해야 합니다.  **Requery** 또는 **Open** 호출에 실패하는 이유는 여러 가지입니다.  네트워크 오류가 발생한 경우, 호출하는 동안 기존 데이터를 해제한 다음 새 데이터를 얻기 전에 다른 사용자가 단독 액세스한 경우, 레코드 집합이 의존하는 테이블이 삭제된 경우 등이 실패 원인이 될 수 있습니다.  
  
## 참고 항목  
 [레코드 집합\(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [레코드 집합: 데이터 열 동적 바인딩\(ODBC\)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)   
 [레코드 집합: 레코드 집합 만들기 및 닫기\(ODBC\)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)