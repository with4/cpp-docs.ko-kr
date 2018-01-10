---
title: "레코드 집합: 레코드 집합 업데이트 레코드 방법 (ODBC) | Microsoft Docs"
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
- ODBC recordsets, updating
- recordsets, editing records
- updating recordsets
- recordsets, updating
ms.assetid: 5ceecc06-7a86-43b1-93db-a54fb1e717c7
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e38f2e62e9aa7b01680e9b2fd1e4a540ee552c3c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="recordset-how-recordsets-update-records-odbc"></a>레코드 집합: 레코드 집합의 레코드 업데이트 방법(ODBC)
MFC ODBC 클래스에이 항목에 적용 됩니다.  
  
 외에도 데이터 원본에서 레코드를 선택 하는 기능, 레코드 집합 수 (선택 사항) 업데이트 또는 선택한 레코드를 삭제 하거나 새 레코드를 추가 합니다. 세 가지 요소에 의해 결정 된 레코드 집합의 updateability: 연결 된 데이터 소스는 업데이트할 수 있는지 여부, 만들어지는 SQL 및 레코드 집합 개체를 만들 때 지정 하는 옵션입니다.  
  
> [!NOTE]
>  되는 SQL 사용자 `CRecordset` 개체를 기반으로 레코드 집합의 업데이트 가능성에 영향을 줄 수 있습니다. 예를 들어 SQL 조인이 포함 또는 **GROUP BY** 절, MFC는 업데이트 시 설정 **FALSE**합니다.  
  
> [!NOTE]
>  이 항목에서 파생 된 개체에 적용 됩니다. `CRecordset` 에서 대량 행 페치 구현 되지 않았습니다. 대량 행 페치를 사용 하는 경우 참조 [레코드 집합: 레코드 페치 대량 (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)합니다.  
  
 이 항목에 설명 합니다.  
  
-   [레코드 집합 업데이트에서 역할이](#_core_your_role_in_recordset_updating) 및 프레임 워크에서는을 수행 합니다.  
  
-   [레코드 집합 편집 버퍼](#_core_the_edit_buffer) 및 [다이너셋와 스냅숏 간의 차이](#_core_dynasets_and_snapshots)합니다.  
  
 [레코드 집합: 어떻게 AddNew, Edit 및 Delete 작업 (ODBC)](../../data/odbc/recordset-how-addnew-edit-and-delete-work-odbc.md) 레코드 집합의 관점에서 이러한 함수의 동작에 설명 합니다.  
  
 [레코드 집합: 자세한 방법에 대 한 업데이트 (ODBC)](../../data/odbc/recordset-more-about-updates-odbc.md) 트랜잭션이 업데이트에 미치는 영향, 레코드 집합을 닫거나 스크롤 업데이트가 진행 중에 미치는 영향 및 업데이트가 다른 업데이트 상호 작용 하는 방법을 설명 하 여 레코드 집합 업데이트 스토리를 완료 합니다. 사용자입니다.  
  
##  <a name="_core_your_role_in_recordset_updating"></a>레코드 집합 업데이트에서 역할  
 다음 표에서 추가, 편집 또는 프레임 워크에서는을 수행 하는 함께 레코드를 삭제할을 레코드 집합을 사용 하 여 사용자의 역할을 보여 줍니다.  
  
### <a name="recordset-updating-you-and-the-framework"></a>레코드 집합 업데이트 중: 하 고 프레임 워크  
  
|사용자|프레임워크|  
|---------|-------------------|  
|데이터 소스 업데이트 (또는 추가) 되는지 확인 합니다.|공급 장치 [CDatabase](../../mfc/reference/cdatabase-class.md) 데이터 소스 업데이트 가능성 또는 추가 테스트를 위한 멤버 함수입니다.|  
|(모든 유형)의 레코드를 업데이트할 수 있는 집합을 엽니다.||  
|레코드 집합을 호출 하 여 업데이트할 수 있는지 여부를 결정 `CRecordset` 업데이트와 같은 함수 `CanUpdate` 또는 `CanAppend`합니다.||  
|레코드 집합을 추가, 편집 및 레코드를 삭제 하는 멤버 함수를 호출 합니다.|레코드 집합 개체와 데이터 원본 간에 데이터를 교환 하는 방법을 관리 합니다.|  
|필요에 따라 트랜잭션을 사용 하 여 업데이트 프로세스를 제어 합니다.|공급 장치 `CDatabase` 트랜잭션을 지원 하는 멤버 함수입니다.|  
  
 트랜잭션에 대 한 자세한 내용은 참조 하십시오. [트랜잭션 (ODBC)](../../data/odbc/transaction-odbc.md)합니다.  
  
##  <a name="_core_the_edit_buffer"></a>편집 버퍼  
 레코드 집합 레코드 집합의 필드 데이터 멤버에 하나의 레코드를 포함 하는 편집 버퍼를 토대로-현재 레코드입니다. 업데이트 작업의 현재 레코드에서 작동 하도록이 버퍼를 사용 합니다.  
  
-   레코드를 추가 하는 경우 편집 버퍼 새 레코드를 작성 하는 데 사용 됩니다. 레코드 추가 완료 하면 이전에 현재 레코드가 현재 다시 됩니다.  
  
-   업데이트 하는 경우 (편집) 레코드를 편집 버퍼 레코드 집합의 필드 데이터 멤버를 새 값으로 설정 하는 데 사용 됩니다. 업데이트를 완료 하는 경우에 업데이트 된 레코드는 할당량이 최신입니다.  
  
 호출 하는 경우 [AddNew](../../mfc/reference/crecordset-class.md#addnew) 또는 [편집](../../mfc/reference/crecordset-class.md#edit), 필요에 따라 나중에 복원할 수 있도록 현재 레코드가 저장 됩니다. 호출 하는 경우 [삭제](../../mfc/reference/crecordset-class.md#delete), 현재 레코드가 저장 되지 않고 삭제 된 것으로 표시 되어 및 다른 레코드로으로 스크롤해야 합니다.  
  
> [!NOTE]
>  편집 버퍼 레코드 삭제에서 역할도 하지 않습니다. 현재 레코드를 삭제 하는 경우 레코드는 삭제 된 것으로 표시 되어 있으며이 레코드 집합 "레코드"에 없는 때까지 다른 레코드를 스크롤할 때.  
  
##  <a name="_core_dynasets_and_snapshots"></a>다이너셋 및 스냅숏  
 [다이너셋](../../data/odbc/dynaset.md) 레코드를 스크롤할 때의 내용을 새로 고칩니다. [스냅숏을](../../data/odbc/snapshot.md) 은 나타내므로 호출 하지 않으면의 내용을 새로 고쳐지지 않습니다, 레코드의 정적 상태 [Requery](../../mfc/reference/crecordset-class.md#requery)합니다. 다이너셋의 모든 기능을 사용 하려면 올바른 수준의 ODBC API 지원에 맞는 ODBC 드라이버와 함께 작업 해야 합니다. 자세한 내용은 참조 [ODBC](../../data/odbc/odbc-basics.md) 및 [다이너셋](../../data/odbc/dynaset.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [레코드 집합 (ODBC)](../../data/odbc/recordset-odbc.md)   
 [레코드 집합: AddNew, Edit 및 Delete의 작동 방식(ODBC)](../../data/odbc/recordset-how-addnew-edit-and-delete-work-odbc.md)