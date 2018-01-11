---
title: "레코드 집합: 레코드 집합 (ODBC) 다시 쿼리 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- recordsets, requerying
- requerying recordsets
- Requery method
- ODBC recordsets, requerying
- refreshing recordsets
ms.assetid: 4ebc3b5b-5b91-4f51-a967-245223c6b8e1
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1445273d29fc521b24fbf04ffc5abec1fadd4e59
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="recordset-requerying-a-recordset-odbc"></a>레코드 집합: 레코드 집합 다시 쿼리(ODBC)
MFC ODBC 클래스에이 항목에 적용 됩니다.  
  
 이 항목에서는 레코드 집합 개체를 사용 하는 방법을 설명 (즉, 새로 고침) 된 경우에 작업을 수행 하는 시기 및 데이터베이스에서 자체는 [Requery](../../mfc/reference/crecordset-class.md#requery) 멤버 함수입니다.  
  
 레코드 집합 다시 쿼리 하는 주요 이유는 것입니다.  
  
-   최신 또는 다른 사용자가 추가 된 레코드 및 (삭제 하는 것은 이미 반영) 다른 사용자가 삭제 된 레코드와 관련해 서 레코드 집합을 가져옵니다.  
  
-   매개 변수 값 변경에 따라 레코드 집합을 새로 고칩니다.  
  
##  <a name="_core_bringing_the_recordset_up_to_date"></a>날짜를 레코드 집합 보기  
 자주 하려는 requery 여 recordset 개체를 다시 최신 상태입니다. 다중 사용자 데이터베이스 환경에서 다른 사용자가 변경할 수 데이터를 레코드 집합의 수명 동안. 레코드 집합에 다른 사용자가 변경한 내용을 반영 하는 경우 및 다른 사용자의 변경 내용을 반영 하는 경우에 대 한 자세한 내용은 참조 [레코드 집합: 레코드 집합의 레코드 업데이트 방법 (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md) 및 [다이너셋](../../data/odbc/dynaset.md).  
  
##  <a name="_core_requerying_based_on_new_parameters"></a>새 매개 변수를 기반으로 다시 쿼리  
 자주-만큼 중요 한 역할-활용 [Requery](../../mfc/reference/crecordset-class.md#requery) 새 매개 변수 값 변경에 따라 레코드 집합을 선택 하는 것입니다.  
  
> [!TIP]
>  쿼리 속도 호출 하는 경우 더 빠른 경우가 훨씬 **Requery** 호출 하는 매개 변수 값을 변경 하 여 **열려** 다시 합니다.  
  
##  <a name="_core_requerying_dynasets_vs.._snapshots"></a>다이너셋 vs를 다시 쿼리 합니다. 스냅숏  
 다이너셋은 동적 최신 데이터를 레코드 집합을 제공 하는 데 때문에 다른 사용자가 추가한을 반영 하도록 하려는 경우에 종종 다이너셋 requery 하려고 합니다. 스냅숏, 반면에 유용 보고서를 작성 하 고, 합계를 계산 하는 등의 작업을 수행할 때 안전 하 게 정적 내용에 사용할 수 있기 때문에 합니다. 그러나 스냅샷을 requery 할 때도 있습니다. 다중 사용자 환경에서 스냅숏 데이터를 다른 사용자가 데이터베이스를 변경할 때 데이터 소스와 동기화를 손실 될 수 있습니다.  
  
#### <a name="to-requery-a-recordset-object"></a>레코드 집합 개체를 다시 쿼리  
  
1.  호출 된 [Requery](../../mfc/reference/crecordset-class.md#requery) 개체의 멤버 함수입니다.  
  
 또는 닫고 원본 레코드를 다시 여세요. 두 경우 모두 새 레코드 집합의 데이터 원본 현재 상태를 나타냅니다.  
  
 예를 들어 참조 [레코드 뷰: 두 번째 레코드 집합에서 목록 상자 채우기](../../data/filling-a-list-box-from-a-second-recordset-mfc-data-access.md)합니다.  
  
> [!TIP]
>  최적화 하기 위해 **Requery** 성능, 레코드 집합의 변경 되지 않도록 [필터](../../data/odbc/recordset-filtering-records-odbc.md) 또는 [정렬](../../data/odbc/recordset-sorting-records-odbc.md)합니다. 호출 하기 전에 매개 변수 값만 변경 **Requery**합니다.  
  
 경우는 **Requery** 호출에 실패 호출을 다시 시도할 수 있습니다; 그렇지 않은 경우 응용 프로그램 정상적으로 종료 해야 합니다. 에 대 한 호출 **Requery** 또는 **열려** 다양 한 이유로 실패할 수 있습니다. 아마도 네트워크 오류가 발생합니다. 또는 호출 하는 동안 상태로 새 데이터를 가져온 기존 데이터를 해제 한 후 다른 사용자 수 가져옵니다 배타적으로 액세스 합니다. 또는 레코드 집합에 의존 하는 테이블을 삭제할 수 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [레코드 집합 (ODBC)](../../data/odbc/recordset-odbc.md)   
 [레코드 집합: 데이터 열 (ODBC)을 동적으로 바인딩](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)   
 [레코드 집합: 레코드 집합 만들기 및 닫기(ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)