---
title: "트랜잭션: 트랜잭션이 미치는 영향 (ODBC) 업데이트 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- transactions, updating recordsets
- ODBC recordsets, transactions
- transactions, rolling back
- CommitTrans method
- Rollback method, ODBC transactions
ms.assetid: 9e00bbf4-e9fb-4332-87fc-ec8ac61b3f68
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 59eb8aecbf2dd2138c8a0469d71364b55fd82774
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="transaction-how-transactions-affect-updates-odbc"></a>트랜잭션: 트랜잭션이 업데이트에 미치는 영향(ODBC)
업데이트는 [데이터 소스](../../data/odbc/data-source-odbc.md) 편집 버퍼 (트랜잭션 외부에서 사용 되는 것과 동일한 방법)를 사용 하 여 트랜잭션 동안 관리 됩니다. 레코드 집합의 필드 데이터 멤버는 전체적으로 레코드 집합 중 일시적으로 백업 하는 현재 레코드를 포함 하는 편집 버퍼 역할는 `AddNew` 또는 **편집**합니다. 중는 **삭제** 작업을 현재 레코드는 트랜잭션 내에서 백업 되지 않습니다. 업데이트가 현재 레코드를 저장 하는 방법 및 편집 버퍼에 대 한 자세한 내용은 참조 [레코드 집합: 레코드 집합의 레코드 업데이트 방법 (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)합니다.  
  
> [!NOTE]
>  대량 행 페치를 구현한 경우 호출할 수 없습니다 `AddNew`, **편집**, 또는 **삭제**합니다. 대신 데이터 원본에 대 한 업데이트를 수행 하기 위해 사용자 고유의 함수를 작성 해야 합니다. 대량 행 페치에 대 한 자세한 내용은 참조 [레코드 집합: 레코드 페치 대량 (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)합니다.  
  
 트랜잭션 동안 `AddNew`, **편집**, 및 **삭제** 작업 커밋 또는 롤백할 수 있습니다. 효과 **CommitTrans** 및 **롤백** 현재 레코드를 편집 버퍼 복원 하지 않을 수 있습니다. 현재 레코드 제대로 복원를 이해 하는 방법을 **CommitTrans** 및 **롤백** 의 멤버 함수 `CDatabase` 의업데이트기능작업`CRecordset`.  
  
##  <a name="_core_how_committrans_affects_updates"></a>CommitTrans 업데이트에 미치는 영향  
 다음 표에서의 효과 설명 **CommitTrans** 트랜잭션에 합니다.  
  
### <a name="how-committrans-affects-updates"></a>CommitTrans 업데이트에 미치는 영향  
  
|작업|데이터 원본의 상태|  
|---------------|---------------------------|  
|`AddNew`및 **업데이트**, 차례로 **CommitTrans**|데이터 원본에 새 레코드가 추가 됩니다.|  
|`AddNew`(없이 **업데이트**), 다음 **CommitTrans**|새 레코드가 손실 됩니다. 레코드를 데이터 원본에 추가 되지 않습니다.|  
|**편집** 및 **업데이트**, 차례로 **CommitTrans**|영역 집합에 데이터 원본을 편집 합니다.|  
|**편집** (없이 **업데이트**), 다음 **CommitTrans**|레코드에 편집 내용이 손실 됩니다. 데이터 원본에서 레코드 그대로 적용 됩니다.|  
|**삭제** 다음 **CommitTrans**|데이터 원본에서 삭제 된 레코드입니다.|  
  
##  <a name="_core_how_rollback_affects_updates"></a>Rollback 트랜잭션에 미치는 영향  
 다음 표에서의 효과 설명 **롤백** 트랜잭션에 합니다.  
  
### <a name="how-rollback-affects-transactions"></a>Rollback 트랜잭션에 미치는 영향  
  
|작업|현재 레코드의 상태|필요한 작업|데이터 원본의 상태|  
|---------------|------------------------------|-------------------|---------------------------|  
|`AddNew`및 **업데이트**, 다음 **롤백**|현재 레코드의 콘텐츠는 새 레코드에 대 한 공간을 만들기 위해 일시적으로 저장 됩니다. 새 레코드 편집 버퍼에 입력 됩니다. 후 **업데이트** 라고, 현재 레코드가 편집 버퍼 복원 됩니다.||데이터 소스에 추가 **업데이트** 속도가 반대로 바뀝니다.|  
|`AddNew`(없이 **업데이트**), 다음 **롤백**|현재 레코드의 콘텐츠는 새 레코드에 대 한 공간을 만들기 위해 일시적으로 저장 됩니다. 편집 버퍼 새 레코드를 포함 합니다.|호출 `AddNew` 편집 버퍼 비어 있는 새 레코드로를 복원 합니다. 호출 또는 **이동**(0) 하 여 이전 값 편집 버퍼를 복원 합니다.|때문에 **업데이트** 가 호출 되지 데이터 원본에 대 한 변경 내용은 없습니다.|  
|**편집** 및 **업데이트**, 다음 **롤백**|현재 레코드는 편집 되지 않은 버전을 임시로 저장 됩니다. 편집 버퍼 콘텐츠를 편집 했습니다. 후 **업데이트** 호출 되는 편집 되지 않은 레코드의 버전은 여전히 일시적으로 저장 됩니다.|*다이너셋*: 스크롤하여 현재 레코드 후 다시 편집 버퍼 레코드의 편집 되지 않은 버전을 복원 합니다.<br /><br /> *스냅숏*: 호출 **Requery** 데이터 소스에서 레코드 집합을 새로 고칠 수 있습니다.|데이터 원본에 변경 **업데이트** 반대가 됩니다.|  
|**편집** (없이 **업데이트**), 다음 **롤백**|현재 레코드는 편집 되지 않은 버전을 임시로 저장 됩니다. 편집 버퍼 콘텐츠를 편집 했습니다.|호출 **편집** 편집 버퍼 레코드의 편집 되지 않은 버전을 복원 합니다.|때문에 **업데이트** 가 호출 되지 데이터 원본에 대 한 변경 내용은 없습니다.|  
|**삭제** 다음 **롤백**|현재 레코드의 내용이 삭제 됩니다.|호출 **Requery** 현재 레코드의 내용을 데이터 소스에서 복원 합니다.|데이터 원본에서 데이터 삭제 속도가 반대로 바뀝니다.|  
  
## <a name="see-also"></a>참고 항목  
 [트랜잭션 (ODBC)](../../data/odbc/transaction-odbc.md)   
 [트랜잭션 (ODBC)](../../data/odbc/transaction-odbc.md)   
 [트랜잭션: 레코드 집합 (ODBC)에서 트랜잭션 수행](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)   
 [CDatabase 클래스](../../mfc/reference/cdatabase-class.md)   
 [CRecordset 클래스](../../mfc/reference/crecordset-class.md)