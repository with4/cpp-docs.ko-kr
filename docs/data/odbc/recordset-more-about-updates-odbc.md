---
title: "레코드 집합: 업데이트에 대한 추가 정보(ODBC) | Microsoft Docs"
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
  - "다중 사용자 환경, 레코드 집합에 대한 업데이트"
  - "ODBC 레코드 집합, 업데이트"
  - "레코드, 업데이트"
  - "레코드 집합, 업데이트"
  - "스크롤, 레코드 집합에 대한 업데이트"
  - "트랜잭션, 레코드 집합 업데이트"
  - "레코드 집합 업데이트"
ms.assetid: 0353a742-d226-4fe2-8881-a7daeffe86cd
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# 레코드 집합: 업데이트에 대한 추가 정보(ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목은 MFC ODBC 클래스에 적용됩니다.  
  
 다음은 이 항목에서 설명하는 내용입니다.  
  
-   [트랜잭션 등 기타 작업이 업데이트에 주는 영향](#_core_how_transactions_affect_updates).  
  
-   [사용자 및 다른 사용자의 업데이트](#_core_your_updates_and_the_updates_of_other_users).  
  
-   [Update와 Delete 멤버 함수에 대한 추가 정보](#_core_more_about_update_and_delete).  
  
> [!NOTE]
>  이 항목은 대량 행 페치가 구현되지 않은 `CRecordset`에서 파생된 개체에 적용됩니다.  대량 행 페치를 구현한 경우 이 내용 중 일부는 적용되지 않습니다.  예를 들어 `AddNew`, **Edit**, **Delete** 및 **Update** 멤버 함수를 호출할 수 없지만 트랜잭션은 수행할 수 있습니다.  대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치\(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)를 참조하십시오.  
  
##  <a name="_core_how_other_operations_affect_updates"></a> 다른 작업이 업데이트에 주는 영향  
 트랜잭션을 완료하기 전에 레코드 집합을 닫거나 스크롤하면 트랜잭션을 사용하여 업데이트를 효과적으로 수행할 수 있게 됩니다.  
  
###  <a name="_core_how_transactions_affect_updates"></a> 트랜잭션이 업데이트에 주는 영향  
 `AddNew`, **Edit** 및 **Delete**의 작동 방식을 이해하는 것 이상으로 [CDatabase](../../mfc/reference/cdatabase-class.md)의 **BeginTrans**, **CommitTrans** 및 **Rollback** 멤버 함수가 [CRecordset](../../mfc/reference/crecordset-class.md)의 업데이트 함수와 함께 작동하는 방식을 이해하는 것이 중요합니다.  
  
 기본적으로 `AddNew`와 **Edit**를 호출한 결과는 **Update**를 호출하는 즉시 데이터 소스에 영향을 줍니다.  **Delete** 호출은 즉시 영향을 줍니다.  그러나 트랜잭션을 설정하여 이러한 호출을 일괄적으로 실행할 수 있습니다.  업데이트된 내용을 영구적으로 만들려면 커밋해야 합니다.  생각이 바뀌면 트랜잭션을 커밋하는 대신 롤백하면 됩니다.  
  
 트랜잭션에 대한 자세한 내용은 [트랜잭션\(ODBC\)](../../data/odbc/transaction-odbc.md)을 참조하십시오.  
  
###  <a name="_core_how_closing_the_recordset_affects_updates"></a> 레코드 집합 닫기가 업데이트에 주는 영향  
 트랜잭션이 진행 중일 때, 즉 [CDatabase::CommitTrans](../Topic/CDatabase::CommitTrans.md) 또는 [CDatabase::Rollback](../Topic/CDatabase::Rollback.md)을 호출하지 않았을 때 레코드 집합 또는 연결된 `CDatabase` 개체를 닫으면 데이터베이스 백엔드가 Microsoft Jet 데이터베이스 엔진이 아닌 경우 트랜잭션이 자동으로 롤백됩니다.  
  
> [!CAUTION]
>  데이터베이스 엔진을 사용하는 경우 명시적 트랜잭션 안에서 레코드 집합을 닫아도 명시적 트랜잭션을 커밋하거나 롤백해야 수정된 행이나 설정된 잠금이 해제됩니다.  명시적 Jet 트랜잭션 안에서든 밖에서든 항상 레코드 집합을 열고 닫는 것이 좋습니다.  
  
###  <a name="_core_how_scrolling_affects_updates"></a> 스크롤이 업데이트에 주는 영향  
 레코드 집합에서 [레코드 집합: 스크롤\(ODBC\)](../../data/odbc/recordset-scrolling-odbc.md)을 수행하면 이전 레코드가 먼저 저장되지 않고 새로운 현재 레코드로 편집 버퍼가 채워집니다.  스크롤할 때 이전에 삭제된 레코드는 건너뜁니다.  `AddNew`나 **Edit** 호출 다음에 **Update**, **CommitTrans** 또는 **Rollback**을 먼저 호출하지 않고 스크롤하면 경고 없이 모든 변경 내용이 손실되고 새 레코드가 편집 버퍼에 저장됩니다.  편집 버퍼는 스크롤한 레코드로 채워지고 저장된 레코드는 해제되며 데이터 소스에서는 아무 것도 변경되지 않습니다.  이는 `AddNew`와 **Edit** 모두에 적용됩니다.  
  
##  <a name="_core_your_updates_and_the_updates_of_other_users"></a> 사용자 및 다른 사용자의 업데이트  
 레코드 집합을 사용하여 데이터를 업데이트하면 업데이트가 다른 사용자에게 영향을 줍니다.  마찬가지로 레코드 집합의 생명 주기 동안 다른 사용자가 업데이트를 하면 영향을 받습니다.  
  
 다중 사용자 환경에서는 사용자가 레코드 집합에서 선택한 동일한 레코드가 포함된 레코드 집합을 다른 사용자가 열 수 있습니다.  검색하기 전에 변경된 레코드의 내용은 레코드 집합에 반영됩니다.  다이너셋은 스크롤할 때마다 레코드를 검색하므로 사용자가 레코드로 스크롤할 때마다 변경 내용을 반영합니다.  반면에 스냅숏은 처음 스크롤할 때 레코드를 검색하므로 레코드로 처음 스크롤하기 전에 변경된 내용만 반영합니다.  
  
 사용자가 레코드 집합을 연 후 다른 사용자가 추가한 레코드는 다시 쿼리하지 않으면 레코드 집합에 표시되지 않습니다.  레코드 집합이 다이너셋인 경우 다른 사용자가 편집한 기존의 레코드로 스크롤하면 다이너셋에 표시됩니다.  레코드 집합이 스냅숏인 경우 스냅숏을 다시 쿼리해야 편집 내용이 표시됩니다.  다른 사용자가 추가하거나 삭제한 레코드를 스냅숏에 표시하거나, 다른 사용자가 추가한 레코드를 다이너셋에 표시하려면 [CRecordset::Requery](../Topic/CRecordset::Requery.md)를 호출하여 레코드 집합을 다시 만듭니다. 다른 사용자가 삭제한 레코드는 다이너셋에 표시됩니다. 또한 **Requery**를 호출하면 추가한 레코드는 볼 수 있지만 삭제한 레코드는 볼 수 없습니다.  
  
> [!TIP]
>  전체 스냅숏을 한 번에 캐시하려면 스냅숏을 연 직후 `MoveLast`를 호출합니다.  그런 다음 **MoveFirst**를 호출하여 레코드 작업을 시작합니다.  `MoveLast`를 호출한 결과는 레코드를 모두 스크롤한 것과 같지만 레코드를 한 번에 검색할 수 있습니다.  그러나 이 경우 성능이 저하되며 일부 드라이버에는 이러한 작업이 필요하지 않을 수도 있습니다.  
  
 사용자의 업데이트가 다른 사용자에게 주는 영향은 다른 사용자의 업데이트가 사용자에게 주는 영향과 유사합니다.  
  
##  <a name="_core_more_about_update_and_delete"></a> Update와 Delete에 대한 추가 정보  
 이 절에서는 **Update**와 **Delete** 작업에 도움이 되는 추가 정보를 제공합니다.  
  
### Update 성공 및 실패  
 **Update**가 성공하면 `AddNew`나 **Edit** 모드가 종료됩니다.  `AddNew`나 **Edit** 모드를 다시 시작하려면 `AddNew`나 **Edit**를 호출합니다.  
  
 **Update**가 실패하면\(즉 **FALSE**가 반환되거나 예외가 throw되면\) 마지막에 호출한 함수에 따라 `AddNew` 또는 **Edit** 모드에 남아 있습니다.  이때 다음 중 하나를 수행할 수 있습니다.  
  
-   필드 데이터 멤버를 수정하고 다시 **Update**를 시도합니다.  
  
-   `AddNew`를 호출하여 필드 데이터 멤버를 Null로 다시 설정하고 필드 데이터 멤버의 값을 설정한 다음 다시 **Update**를 호출합니다.  
  
-   **Edit**를 호출하여 `AddNew`나 **Edit**를 처음 호출하기 전에 레코드 집합에 있던 값을 다시 로드한 다음 필드 데이터 멤버의 값을 설정하고 **Update**를 다시 호출합니다.  **Update** 호출\(`AddNew` 호출은 제외\)이 성공한 후 필드 데이터 멤버는 새 값을 유지합니다.  
  
-   **Move**\(매개 변수가 **AFX\_MOVE\_REFRESH** 또는 0인 **Move** 포함\)를 호출하여 효과적으로 모든 변경 내용을 플러시하고 `AddNew` 또는 **Edit** 모드를 끝냅니다.  
  
### Update 및 Delete  
 이 절의 내용은 **Update**와 **Delete** 모두에 적용됩니다.  
  
 **Update** 또는 **Delete** 작업에서는 레코드 하나만 업데이트해야 합니다.  그 레코드는 레코드 집합의 필드에 있는 데이터 값에 상응하는 현재 레코드입니다.  어떤 이유로 영향을 받은 레코드가 없거나 둘 이상이면 다음 **RETCODE** 값 중 하나를 포함하는 예외가 throw됩니다.  
  
-   **AFX\_SQL\_ERROR\_NO\_ROWS\_AFFECTED**  
  
-   **AFX\_SQL\_ERROR\_MULTIPLE\_ROWS\_AFFECTED**  
  
 이런 예외가 throw되면 **Update** 또는 **Delete**를 호출했을 때의 `AddNew` 또는 **Edit** 상태가 유지됩니다.  다음은 이러한 예외를 볼 수 있는 가장 일반적인 시나리오로서  다음과 같은 값이 나타납니다.  
  
-   **AFX\_SQL\_ERROR\_NO\_ROWS\_AFFECTED** 낙관적 잠금 모드를 사용하고 있고 업데이트 또는 삭제할 올바른 레코드를 프레임워크가 식별하지 못하도록 다른 사용자가 레코드를 수정한 경우  
  
-   **AFX\_SQL\_ERROR\_MULTIPLE\_ROWS\_AFFECTED** 업데이트하고 있는 테이블에 기본 키 또는 고유 인덱스가 없고 테이블 행을 고유하게 식별하기 위해 필요한 열이 레코드 집합에 충분히 없는 경우  
  
## 참고 항목  
 [레코드 집합\(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [레코드 집합: 레코드 집합의 레코드 선택 방법\(ODBC\)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)   
 [RFX](../../data/odbc/record-field-exchange-rfx.md)   
 [SQL](../../data/odbc/sql.md)   
 [예외: 데이터베이스 예외](../../mfc/exceptions-database-exceptions.md)