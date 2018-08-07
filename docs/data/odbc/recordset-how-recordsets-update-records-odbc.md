---
title: '레코드 집합: 레코드 집합 업데이트 레코드 방법 (ODBC) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- records, updating
- ODBC recordsets, updating
- recordsets, editing records
- updating recordsets
- recordsets, updating
ms.assetid: 5ceecc06-7a86-43b1-93db-a54fb1e717c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2697952b500c7643bf0723c99395e56ebc48ad84
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39340705"
---
# <a name="recordset-how-recordsets-update-records-odbc"></a>레코드 집합: 레코드 집합의 레코드 업데이트 방법(ODBC)
이 항목에서는 MFC ODBC 클래스에 적용 됩니다.  
  
 데이터 원본에서 레코드를 선택 하는 기능, 외에도 레코드 집합 수 (선택 사항) 업데이트 선택한 레코드를 삭제 또는 새 레코드를 추가 합니다. 세 가지 요소를 레코드 집합의 업데이트를 확인 합니다: 연결된 된 데이터 소스를 업데이트할 수 있는지 여부, 만든 SQL 및 레코드 집합 개체를 만들 때 지정 하는 옵션입니다.  
  
> [!NOTE]
>  SQL 사용자 `CRecordset` 개체를 기반으로 레코드 집합의 업데이트에 영향을 줄 수 있습니다. 예를 들어 SQL 조인을 포함 하는 경우 **GROUP BY** 절, MFC의 updateability FALSE로 설정 합니다.  
  
> [!NOTE]
>  이 항목에서 파생 된 개체에 적용 됩니다 `CRecordset` 의 대량 행 페치 구현 되지 않았습니다. 대량 행 페치를 사용 하는 경우 참조 [레코드 집합: 레코드 페치 대량 (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)합니다.  
  
 이 항목에 설명 합니다.  
  
-   [레코드 집합 업데이트에서 역할이](#_core_your_role_in_recordset_updating) 및 프레임 워크 역할 수 있습니다.  
  
-   [레코드 집합 편집 버퍼로](#_core_the_edit_buffer) 하며 [다이너셋와 스냅숏 간의 차이](#_core_dynasets_and_snapshots)합니다.  
  
 [레코드 집합: 어떻게 AddNew, Edit 및 삭제 작업 (ODBC)](../../data/odbc/recordset-how-addnew-edit-and-delete-work-odbc.md) 레코드 집합의 관점에서 이러한 함수는 작업을 설명 합니다.  
  
 [레코드 집합: 추가 대 한 업데이트 정보 (ODBC)](../../data/odbc/recordset-more-about-updates-odbc.md) 트랜잭션이 업데이트에 미치는 영향, 레코드 집합을 닫거나 스크롤 업데이트가 진행에서에 미치는 영향 및 업데이트가 다른 업데이트 상호 작용 하는 방법을 설명 하 여 레코드 집합 업데이트 스토리를 완료 합니다. 사용자입니다.  
  
##  <a name="_core_your_role_in_recordset_updating"></a> 레코드 집합 업데이트의 역할  
 다음 표에서 추가, 편집 또는 삭제 레코드 수에 대 한 용도 프레임 워크와 함께 레코드 집합을 사용 하 여 사용자의 역할을 보여 줍니다.  
  
### <a name="recordset-updating-you-and-the-framework"></a>레코드 집합 업데이트: 하 고 프레임 워크  
  
|사용자|프레임워크|  
|---------|-------------------|  
|데이터 원본 업데이트 (또는 추가) 인지 확인 합니다.|공급 [CDatabase](../../mfc/reference/cdatabase-class.md) 데이터 원본의 updateability 또는 추가 테스트에 대 한 멤버 함수입니다.|  
|(모든 유형)의 레코드를 업데이트할 수 있는 집합을 엽니다.||  
|호출 하 여 레코드 집합을 업데이트할 수 있는지 여부를 결정 `CRecordset` 와 같은 함수를 업데이트 `CanUpdate` 또는 `CanAppend`합니다.||  
|레코드 집합 추가, 편집 및 레코드를 삭제 하는 멤버 함수를 호출 합니다.|레코드 집합 개체 및 데이터 원본 간에 데이터를 교환에 대 한 메커니즘을 관리 합니다.|  
|필요에 따라 트랜잭션을 사용 하 여 업데이트 프로세스를 제어 합니다.|제공 `CDatabase` 트랜잭션을 지원 하는 멤버 함수입니다.|  
  
 트랜잭션에 대 한 자세한 내용은 참조 하세요. [트랜잭션 (ODBC)](../../data/odbc/transaction-odbc.md)합니다.  
  
##  <a name="_core_the_edit_buffer"></a> 편집 버퍼  
 레코드 집합 레코드 집합의 필드 데이터 멤버에 하나의 레코드를 포함 하는 편집 버퍼를 역할도-현재 레코드입니다. 현재 레코드에서 동작 하려면이 버퍼를 사용 하는 업데이트 작업.  
  
-   레코드를 추가 하는 경우 새 레코드를 작성 하려면 편집 버퍼로 사용 됩니다. 레코드 추가 완료 하면 이전에 현재 레코드 다시 현재 됩니다.  
  
-   업데이트할 때 새 값으로 레코드 집합의 필드 데이터 멤버를 설정 (편집) 레코드를 편집 버퍼가 됩니다. 업데이트를 완료 하면 업데이트 된 레코드는 여전히 있습니다.  
  
 호출 하는 경우 [AddNew](../../mfc/reference/crecordset-class.md#addnew) 하거나 [편집](../../mfc/reference/crecordset-class.md#edit), 현재 레코드, 필요에 따라 나중에 복원할 수 있도록 저장 됩니다. 호출 하는 경우 [삭제](../../mfc/reference/crecordset-class.md#delete)스크롤해야 다른 레코드를 현재 레코드에 저장 되지 않고 삭제 된 것으로 표시 됩니다.  
  
> [!NOTE]
>  편집 버퍼 아무 역할도 레코드를 삭제 합니다. 현재 레코드를 삭제 하면 레코드는 삭제에 표시 되 고 다른 레코드를 스크롤할 때까지 레코드는 "레코드"에 없습니다.  
  
##  <a name="_core_dynasets_and_snapshots"></a> 다이너셋 및 스냅숏  
 [다이너셋](../../data/odbc/dynaset.md) 레코드를 스크롤할 때의 내용을 새로 고칩니다. [스냅숏을](../../data/odbc/snapshot.md) 레코드의 정적 표현 되므로 레코드의 콘텐츠를 호출 하지 않으면 새로 고쳐지지 않습니다 [Requery](../../mfc/reference/crecordset-class.md#requery)합니다. 다이너셋의 모든 기능을 사용 하려면 올바른 수준의 ODBC API 지원에 따르는 ODBC 드라이버를 사용 하 여 작업 해야 합니다. 자세한 내용은 [ODBC](../../data/odbc/odbc-basics.md) 하 고 [다이너셋](../../data/odbc/dynaset.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [레코드 집합 (ODBC)](../../data/odbc/recordset-odbc.md)   
 [레코드 집합: AddNew, Edit 및 Delete의 작동 방식(ODBC)](../../data/odbc/recordset-how-addnew-edit-and-delete-work-odbc.md)