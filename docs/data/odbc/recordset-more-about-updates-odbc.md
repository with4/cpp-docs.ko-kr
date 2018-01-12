---
title: "레코드 집합:에 대 한 업데이트 (ODBC) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- records, updating
- transactions, updating recordsets
- ODBC recordsets, updating
- multiuser environments, updates to recordsets
- scrolling, updates to recordsets
- updating recordsets
- recordsets, updating
ms.assetid: 0353a742-d226-4fe2-8881-a7daeffe86cd
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1ad9042c4001fc1a0e0c8c8d19e5ac53b6312875
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="recordset-more-about-updates-odbc"></a>레코드 집합: 업데이트에 대한 추가 정보(ODBC)
MFC ODBC 클래스에이 항목에 적용 됩니다.  
  
 이 항목에 설명 합니다.  
  
-   [트랜잭션, 등의 다른 작업 업데이트에 미치는 영향](#_core_how_transactions_affect_updates)합니다.  
  
-   [업데이트 및 다른 사용자의](#_core_your_updates_and_the_updates_of_other_users)합니다.  
  
-   [Update 및 Delete 멤버 함수에 대 한 자세한](#_core_more_about_update_and_delete)합니다.  
  
> [!NOTE]
>  이 항목에서 파생 된 개체에 적용 됩니다. `CRecordset` 에서 대량 행 페치 구현 되지 않았습니다. 대량 행 페치를 구현한 경우이 정보 중 일부는 적용 되지 않습니다. 예를 들어, 호출할 수 없습니다는 `AddNew`, **편집**, **삭제**, 및 **업데이트** 멤버 함수입니다; 그러나 트랜잭션을 수행할 수 있습니다. 대량 행 페치에 대 한 자세한 내용은 참조 [레코드 집합: 레코드 페치 대량 (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)합니다.  
  
##  <a name="_core_how_other_operations_affect_updates"></a>다른 작업 업데이트에 미치는 영향  
 업데이트는와 영향을 트랜잭션에 의해 적용 업데이트의 시간에는 트랜잭션을 완료 하기 전에 레코드 집합을 닫거나 트랜잭션을 완료 하기 전에 스크롤.  
  
###  <a name="_core_how_transactions_affect_updates"></a>트랜잭션이 업데이트에 미치는 영향  
 이해 외 어떻게 `AddNew`, **편집**, 및 **삭제** 가 이해 하는 것이 중요 작업을 방법을 **BeginTrans**, **CommitTrans**, 및 **롤백** 의 멤버 함수 [CDatabase](../../mfc/reference/cdatabase-class.md) 의 업데이트 기능 관련 작업을 수행할 [CRecordset](../../mfc/reference/crecordset-class.md)합니다.  
  
 에 대 한 호출이 기본적으로 `AddNew` 및 **편집** 즉시 호출 하는 경우 데이터 원본에 영향을 줍니다. **업데이트**합니다. **삭제** 호출 즉시 적용 합니다. 하지만 트랜잭션을 설정 하 고 이러한 호출의 일괄 처리를 실행할 수 있습니다. 커밋할 때까지 업데이트 저장 되지 않습니다. 생각이 바뀌었다 면 경우 롤백할 수 있습니다 트랜잭션을 커밋하는 대신 합니다.  
  
 트랜잭션에 대 한 자세한 내용은 참조 하십시오. [트랜잭션 (ODBC)](../../data/odbc/transaction-odbc.md)합니다.  
  
###  <a name="_core_how_closing_the_recordset_affects_updates"></a>레코드 집합을 닫으면 업데이트에 미치는 영향  
 레코드 집합 또는 연결 된 해당 닫으면 `CDatabase` 진행 중인 트랜잭션 사용 하 여 개체 (호출 하지 않은 [CDatabase::CommitTrans](../../mfc/reference/cdatabase-class.md#committrans) 또는 [CDatabase::Rollback](../../mfc/reference/cdatabase-class.md#rollback)), 트랜잭션이 롤백됩니다. 자동으로 ()를 제외 하면 데이터베이스 백 엔드가 Microsoft Jet 데이터베이스 엔진을 백업 합니다.  
  
> [!CAUTION]
>  Microsoft Jet 데이터베이스 엔진을 사용 하는 경우를 명시적 트랜잭션 내 레코드 집합을 닫으면 되지 않습니다 수정 된 행 이나 명시적 트랜잭션이 커밋되거나 롤백될 때까지 접수 된 잠금을 해제 합니다. 해당 하면 항상 모두 닫기 레코드 집합을 열고 내부 또는 외부 명시적 Jet 트랜잭션 것이 좋습니다.  
  
###  <a name="_core_how_scrolling_affects_updates"></a>스크롤 업데이트에 미치는 영향  
 때 있습니다 [레코드 집합: 스크롤 (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) 는 레코드 집합에서 편집 버퍼 새로운 현재 레코드로 (이전 레코드 먼저 저장 되지 않음)으로 채워집니다. 이전에 삭제 한 레코드를 통해 건너뜁니다 스크롤입니다. 후 스크롤하면는 `AddNew` 또는 **편집** 호출 하지 않고 호출 **업데이트**, **CommitTrans**, 또는 **롤백** 첫 번째, 모든 변경 내용 새 레코드를 편집 버퍼에 의해 되 게 경고 메시지) (없이 손실입니다. 편집 버퍼 스크롤한 레코드로 채워집니다, 그리고 저장된 된 레코드 해제 되 면 및 변경 데이터 원본에 대해 발생 합니다. 이 둘 다에 적용 됩니다 `AddNew` 및 **편집**합니다.  
  
##  <a name="_core_your_updates_and_the_updates_of_other_users"></a>업데이트 및 다른 사용자의 업데이트  
 레코드 집합을 사용 하 여 데이터를 업데이트 하려면 업데이트 내용을 다른 사용자에 게를 영향을 줍니다. 마찬가지로, 레코드 집합의 수명 동안 다른 사용자의 업데이트를 영향을 있습니다.  
  
 다중 사용자 환경에서 다른 사용자가 레코드 집합에서 선택한 동일한 레코드가 포함 된 레코드 집합을 열 수 있습니다. 레코드 집합에는 레코드를 검색 하기 전에 변경 내용이 반영 됩니다. 다이너셋 스크롤할 때 레코드를 검색, 때문에 레코드를 스크롤할 때마다 변경 내용을 반영 합니다. 스냅숏을 하므로 처음에 레코드를 스크롤하기 전에 발생 하는 변경 내용만 반영을 스크롤할 때 레코드를 검색 합니다.  
  
 레코드 집합을 연 후 다른 사용자가 추가한 레코드 않습니다 다시 쿼리하지 않는 한 레코드 집합에 나타나지 않습니다. 다이너셋 레코드 집합을 사용 하는 경우 다른 사용자가 기존 레코드에 대 한 편집 표시지 않습니다 다이너셋에 영향을 받은 레코드를 스크롤할 때. 레코드 집합 스냅숏일 경우 편집 스냅숏을 다시 쿼리까지 표시 되지 않습니다. 호출 스냅숏 또는 다이너셋에 다른 사용자가 추가 된 레코드의 다른 사용자가 삭제 또는 추가 된 레코드를 참조 하려면 [>crecordset:: Requery](../../mfc/reference/crecordset-class.md#requery) 레코드 집합 다시 작성 해야 합니다. (다이너셋에 다른 사용자가 삭제 표시 참고 합니다.) 또한 호출 **Requery** 레코드를 볼 수를 추가 하면 되지만 삭제 참조 하지 않습니다.  
  
> [!TIP]
>  스냅숏을 한 번에 전체 캐시 하려면, 호출 `MoveLast` 스냅숏을 연 후에 즉시 합니다. 그런 다음 호출 **MoveFirst** 작업 레코드를 시작 합니다. `MoveLast`모든 레코드 스크롤에 해당 하지만 한 번에 모두 검색 합니다. 단,이 성능이 저하 되며 일부 드라이버에 대 한 필요 없을 수도 있습니다.  
  
 다른 사용자에 대 한 업데이트의 효과 사용자에 대 한 영향 비슷합니다.  
  
##  <a name="_core_more_about_update_and_delete"></a>업데이트 및 삭제에 대 한 자세한 정보  
 이 섹션에서는 작업할 수 있도록 추가 정보를 제공 **업데이트** 및 **삭제**합니다.  
  
### <a name="update-success-and-failure"></a>업데이트 성공 및 실패  
 경우 **업데이트** 성공 하면는 `AddNew` 또는 **편집** 모드 종료 합니다. 시작 하려면 프로그램 `AddNew` 또는 **편집** 다시 모드, 호출 `AddNew` 또는 **편집**합니다.  
  
 경우 **업데이트** 실패 (반환 **FALSE** 하거나 예외를 throw)에 계속 남아 있는 `AddNew` 또는 **편집** 함수에 따라 호출 마지막 모드입니다. 다음 중 하나를 수행할 수 있습니다.  
  
-   필드 데이터 멤버를 수정 하 고 시도 **업데이트** 다시 합니다.  
  
-   호출 `AddNew` 필드 데이터 멤버를 Null로 다시 설정 하려면 필드 데이터 멤버의 값을 설정 하 고 다음 호출할 **업데이트** 다시 합니다.  
  
-   호출 **편집** 처음 호출 하기 전에 레코드 집합에 있는 값을 다시 로드 하려면 `AddNew` 또는 **편집**필드 데이터 멤버의 값을 설정 하 고, 다음 호출 **업데이트**다시 합니다. 성공 후 **업데이트** 호출 (이후는 제외는 `AddNew` 호출)를 필드 데이터 멤버는 새 값을 유지 합니다.  
  
-   호출 **이동** (포함 하 여 **이동** 의 매개 변수와 함께 **AFX_MOVE_REFRESH**, 또는 0)는 모든 변경 플러시하고 모든 종료 `AddNew` 또는 **편집** 적용에서 모드입니다.  
  
### <a name="update-and-delete"></a>업데이트 및 삭제  
 이 섹션은 둘 다에 적용 됩니다. **업데이트** 및 **삭제**합니다.  
  
 에 **업데이트** 또는 **삭제** 작업의 경우 하나의 레코드를 업데이트 해야 합니다. 해당 레코드는 레코드 집합의 필드에 있는 데이터 값에 해당 하는 현재 레코드입니다. 다음 중 하나를 포함 하는 예외가 throw 된 어떤 레코드가 없는 영향을 받는 또는 하나 이상의 레코드는 영향을 이유로 경우 **RETCODE** 값:  
  
-   **AFX_SQL_ERROR_NO_ROWS_AFFECTED**  
  
-   **AFX_SQL_ERROR_MULTIPLE_ROWS_AFFECTED**  
  
 이러한 예외가 throw 되 면에 계속 남아 있는 `AddNew` 또는 **편집** 호출 했을 때에 있었을 상태 **업데이트** 또는 **삭제**합니다. 다음은 이러한 예외를 볼 수 있는 가장 일반적인 시나리오입니다. 했으면이 나타납니다.  
  
-   **AFX_SQL_ERROR_NO_ROWS_AFFECTED** 낙관적 잠금 모드와 다른 사용자를 사용할 경우 프레임 워크를 업데이트 하거나 삭제할 올바른 레코드를 식별 하지 못하게 하는 방법의 레코드를 수정 했습니다.  
  
-   **AFX_SQL_ERROR_MULTIPLE_ROWS_AFFECTED** 때 업데이트 하는 테이블에 기본 키 또는 고유 인덱스와 있습니다 수 있는 열에에서 없는 테이블 행을 고유 하 게 식별 하는 레코드 집합입니다.  
  
## <a name="see-also"></a>참고 항목  
 [레코드 집합 (ODBC)](../../data/odbc/recordset-odbc.md)   
 [레코드 집합: 레코드 집합 선택 레코드 방법 (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)   
 [레코드 필드 교환 (RFX)](../../data/odbc/record-field-exchange-rfx.md)   
 [SQL](../../data/odbc/sql.md)   
 [예외: 데이터베이스 예외](../../mfc/exceptions-database-exceptions.md)