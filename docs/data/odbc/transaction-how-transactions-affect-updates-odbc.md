---
title: "트랜잭션: 트랜잭션이 업데이트에 미치는 영향(ODBC) | Microsoft Docs"
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
  - "CommitTrans 메서드"
  - "ODBC 레코드 집합, 트랜잭션"
  - "Rollback 메서드, ODBC 트랜잭션"
  - "트랜잭션, 롤백"
  - "트랜잭션, 레코드 집합 업데이트"
ms.assetid: 9e00bbf4-e9fb-4332-87fc-ec8ac61b3f68
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# 트랜잭션: 트랜잭션이 업데이트에 미치는 영향(ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[데이터 소스](../../data/odbc/data-source-odbc.md)의 업데이트는 트랜잭션 동안 편집 버퍼를 사용하여 관리됩니다\(트랜잭션 외부에서 사용되는 것과 동일한 방법\).  레코드 집합의 필드 데이터 멤버는 전체적으로 현재 레코드를 포함한 편집 버퍼의 역할을 하며 `AddNew` 또는 **Edit**를 수행하는 동안 레코드 집합을 임시로 백업합니다.  **Delete**를 수행하는 동안 현재 레코드는 트랜잭션에서 백업되지 않습니다.  업데이트가 현재 레코드를 저장하는 방법 및 편집 버퍼에 대한 자세한 내용은 [레코드 집합: 레코드 집합의 레코드 업데이트 방법\(ODBC\)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)을 참조하십시오.  
  
> [!NOTE]
>  대량 행 페치를 구현한 경우 `AddNew`, **Edit** 또는 **Delete**를 호출할 수 없습니다.  대신 직접 데이터 소스를 업데이트하는 함수를 작성해야 합니다.  대량 행 페치에 대한 자세한 내용은 [레코드 집합: 대량 레코드 페치\(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)를 참조하십시오.  
  
 트랜잭션 동안 `AddNew`, **Edit** 및 **Delete** 작업이 수행되거나 롤백됩니다.  **CommitTrans**와 **Rollback**의 영향으로 인해 현재 레코드가 편집 버퍼로 복원되지 못할 수도 있습니다.  현재 레코드를 제대로 복원하려면 `CDatabase`의 **CommitTrans**와 **Rollback** 멤버 함수가 `CRecordset`의 Update 함수를 다루는 방식을 이해하는 것이 중요합니다.  
  
##  <a name="_core_how_committrans_affects_updates"></a> CommitTrans가 업데이트에 미치는 영향  
 다음 표는 트랜잭션에서 **CommitTrans**의 효과에 대한 설명입니다.  
  
### CommitTrans가 업데이트에 미치는 영향  
  
|작업|데이터 소스의 상태|  
|--------|----------------|  
|`AddNew` 및 **Update** 다음에 **CommitTrans**|데이터 소스에 새 레코드가 추가됩니다.|  
|`AddNew`\(**Update** 없이\) 다음에 **CommitTrans**|새 레코드를 잃게 됩니다.  데이터 소스에 레코드가 추가되지 않습니다.|  
|**Edit** 및 **Update** 다음에 **CommitTrans**|데이터 소스에 대해 편집 버퍼의 내용이 커밋됩니다.|  
|**Edit**\(**Update** 없이\) 다음에 **CommitTrans**|레코드에 대해 편집 버퍼의 내용을 잃게 됩니다.  데이터 소스에서 레코드가 변경되지 않습니다.|  
|**Delete** 다음에 **CommitTrans**|데이터 소스에서 레코드가 삭제됩니다.|  
  
##  <a name="_core_how_rollback_affects_updates"></a> Rollback이 트랜잭션에 미치는 영향  
 다음 표는 트랜잭션에서 **Rollback**의 효과에 대한 설명입니다.  
  
### Rollback이 트랜잭션에 미치는 영향  
  
|작업|현재 레코드의 상태|필요한 작업|데이터 소스의 상태|  
|--------|----------------|------------|----------------|  
|`AddNew` 및 **Update** 다음에 **Rollback**|새 레코드의 공간을 확보하기 위해 현재 레코드의 내용이 임시로 저장됩니다.  새 레코드가 편집 버퍼로 들어갑니다.  **Update**를 호출한 다음 편집 버퍼에서 현재 레코드가 복원됩니다.||**Update**에 의해 데이터 소스에 추가된 내용이 취소됩니다.|  
|`AddNew`\(**Update** 없이\) 다음에 **Rollback**|새 레코드의 공간을 확보하기 위해 현재 레코드의 내용이 임시로 저장됩니다.  편집 버퍼에 새 레코드가 포함됩니다.|`AddNew`를 다시 호출하여 편집 버퍼를 비어 있는 새 레코드로 복원합니다.  또는 **Move**\(0\)를 호출하여 이전의 값을 편집 버퍼로 복원합니다.|**Update**가 호출되지 않았기 때문에 데이터 소스가 변경되지 않습니다.|  
|**Edit** 및 **Update** 다음에 **Rollback**|현재 레코드의 편집되지 않은 버전이 임시로 저장됩니다.  편집 버퍼의 내용이 편집됩니다.  **Update**가 호출된 다음에도 레코드의 편집되지 않은 버전은 임시로 저장되어 있습니다.|*Dynaset*: 현재 레코드를 스크롤하여 이동한 다음 되돌아와 편집되지 않은 레코드 버전을 편집 버퍼로 복원합니다.<br /><br /> *Snapshot*: **Requery**를 호출하여 데이터 소스에서 레코드 집합을 새로 고칩니다.|**Update**에 의해 데이터 소스에 추가된 내용이 취소됩니다.|  
|**Edit**\(**Update** 없이\) 다음에 **Rollback**|현재 레코드의 편집되지 않은 버전이 임시로 저장됩니다.  편집 버퍼의 내용이 편집됩니다.|**Edit**를 다시 호출하여 편집되지 않은 레코드 버전을 편집 버퍼로 복원합니다.|**Update**가 호출되지 않았기 때문에 데이터 소스가 변경되지 않습니다.|  
|**Delete** 다음에 **Rollback**|현재 레코드의 내용이 삭제되었습니다.|**Requery**를 호출하여 데이터 소스로부터 현재 레코드의 내용을 복원합니다.|데이터 소스에서 데이터 삭제가 취소됩니다.|  
  
## 참고 항목  
 [트랜잭션\(ODBC\)](../../data/odbc/transaction-odbc.md)   
 [트랜잭션\(ODBC\)](../../data/odbc/transaction-odbc.md)   
 [트랜잭션: 레코드 집합에서 트랜잭션 수행\(ODBC\)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)   
 [CDatabase Class](../../mfc/reference/cdatabase-class.md)   
 [CRecordset Class](../../mfc/reference/crecordset-class.md)