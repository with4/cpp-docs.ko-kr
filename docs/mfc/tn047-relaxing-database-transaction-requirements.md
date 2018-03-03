---
title: "TN047: 데이터베이스 트랜잭션 요구 사항 완화 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.data
dev_langs:
- C++
helpviewer_keywords:
- TN047
ms.assetid: f93c51cf-a8c0-43d0-aa47-7bcb8333d693
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 92631d96e8782a80275695ef4bf2623dc1bff833
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="tn047-relaxing-database-transaction-requirements"></a>TN047: 데이터베이스 트랜잭션 요구 사항 완화
MFC ODBC 데이터베이스 클래스의 트랜잭션 요구 사항 설명,이 기술 노트는 이제 사용 되지 않습니다. MFC 4.2 하기 전에 데이터베이스 클래스 커서 후 레코드 집합에 유지 될 필요는 **CommitTrans** 또는 **롤백** 작업 합니다. ODBC 드라이버 및 DBMS 커서 유지의이 수준을 지원 하지 않은 경우 데이터베이스 클래스 트랜잭션을 활성화 하지 않은 것입니다.  
  
 데이터베이스 클래스는 MFC 4.2 부터는 커서 보존을 요구할 때의 제한을 완화 했습니다. 트랜잭션을은 드라이버가 지 원하는 경우에 설정 됩니다. 하지만 효과 지금 확인 해야 한 **CommitTrans** 또는 **롤백** 열려 있는 레코드 집합이 대 한 작업이 있습니다. 멤버 함수를 참조 하십시오. [CDatabase::GetCursorCommitBehavior](../mfc/reference/cdatabase-class.md#getcursorcommitbehavior) 및 [CDatabase::GetCursorRollbackBehavior](../mfc/reference/cdatabase-class.md#getcursorrollbackbehavior) 자세한 정보에 대 한 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)   
 [범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)

