---
title: "탭 컨트롤 알림 메시지 처리 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- notifications [MFC], tab controls
- CTabCtrl class [MFC], processing notifications
- notifications [MFC], processing in CTabCtrl
- processing notifications [MFC]
- tab controls [MFC], processing notifications
ms.assetid: 758ccb7a-9e73-48f8-9073-23f7cb09918c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 840ff6fc5dd47a2059e62608b5a5d6f231f8f17c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="processing-tab-control-notification-messages"></a>탭 컨트롤 알림 메시지 처리
사용자가 탭 또는 단추, 탭 컨트롤을 클릭할 때 ([CTabCtrl](../mfc/reference/ctabctrl-class.md))를 해당 부모 창 알림 메시지를 보냅니다. 이에 대한 응답으로 작업을 수행하려는 경우 이러한 메시지를 처리합니다. 예를 들어 사용자가 탭을 클릭할 때 컨트롤 데이터를 표시 하기에 앞서 사전 설정 하는 것이 좋습니다.  
  
 프로세스 **WM_NOTIFY** 뷰 또는 대화 상자 클래스에서 탭 컨트롤의 메시지입니다. 속성 창을 사용 하 여 만들기는 [OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify) switch 문 사용 하는 처리기 함수는 알림 메시지 처리 되 고 기반 합니다. 탭 컨트롤은 해당 부모 창에 보낼 수 알림 목록에 대 한 참조는 **알림** 의 섹션 [탭 컨트롤 참조](http://msdn.microsoft.com/library/windows/desktop/bb760548) Windows sdk에서입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CTabCtrl 사용](../mfc/using-ctabctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

