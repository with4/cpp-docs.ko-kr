---
title: "TN047: 데이터베이스 트랜잭션 요구 사항 완화 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.data"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "TN047"
ms.assetid: f93c51cf-a8c0-43d0-aa47-7bcb8333d693
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# TN047: 데이터베이스 트랜잭션 요구 사항 완화
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

This tech note, which discussed the transaction requirements of the MFC ODBC database classes, is now obsolete.  Before MFC 4.2, the database classes required that cursors be preserved on recordsets after a **CommitTrans** or **Rollback** operation.  If the ODBC driver and DBMS did not support this level of cursor preservation, then the database classes did not enable transactions.  
  
 Beginning with MFC 4.2, the database classes have relaxed the restriction of requiring cursor preservation.  Transactions will be enabled if the driver supports them.  However, you must now check the effect of a **CommitTrans** or **Rollback** operation on open recordsets.  See the member functions [CDatabase::GetCursorCommitBehavior](../Topic/CDatabase::GetCursorCommitBehavior.md) and [CDatabase::GetCursorRollbackBehavior](../Topic/CDatabase::GetCursorRollbackBehavior.md) for more information.  
  
## 참고 항목  
 [번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)   
 [범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)