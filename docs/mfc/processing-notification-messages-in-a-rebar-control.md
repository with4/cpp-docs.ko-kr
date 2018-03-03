---
title: "Rebar 컨트롤에서 알림 메시지 처리 | Microsoft Docs"
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
- RBN_ notification messages, description of
- CReBarCtrl class [MFC], notification messages sent by
- RBN_ notification messages [MFC]
- notifications [MFC], CReBarCtrl
ms.assetid: 40f43a60-0c18-4d8d-8fab-213a095624f9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 22a8b584c309cd6698ddd73449fcbba866111190
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="processing-notification-messages-in-a-rebar-control"></a>Rebar 컨트롤에서 알림 메시지 처리
Rebar 컨트롤의 부모 클래스에서 만듭니다는 `OnChildNotify` 모든 rebar 컨트롤에 대해 switch 문 사용 하는 처리기 함수 (`CReBarCtrl`) 알림 메시지를 처리 합니다. 개체 변경 내용 삭제 rebar 밴드의 레이아웃 및 등 rebar 컨트롤에서 밴드 rebar 컨트롤 위로 끌 때 부모 창에 알림이 전송 됩니다.  
  
 Rebar 컨트롤 개체에 의해 다음 알림 메시지를 보낼 수 있습니다.  
  
-   **RBN_AUTOSIZE** rebar 컨트롤에서 보냅니다. (사용 하 여 만든는 **RBS_AUTOSIZE** 스타일) 때 rebar 자동 크기를 조정 합니다.  
  
-   **RBN_BEGINDRAG** 밴드를 끌기 시작할 때 rebar 컨트롤에서 보냅니다.  
  
-   **RBN_CHILDSIZE** 밴드의 자식 창 크기를 조정할 때 rebar 컨트롤에서 보냅니다.  
  
-   **RBN_DELETEDBAND** 밴드 삭제 한 후 rebar 컨트롤에서 보냅니다.  
  
-   **RBN_DELETINGBAND** 밴드를 삭제 하려고 할 때 rebar 컨트롤에서 보냅니다.  
  
-   **RBN_ENDDRAG** 는 사용자는 밴드 끌기를 멈추면 rebar 컨트롤에서 보냅니다.  
  
-   **RBN_GETOBJECT** rebar 컨트롤에서 보냅니다. (사용 하 여 만든는 **RBS_REGISTERDROP** 스타일)는 개체를 컨트롤의 밴드 위로 끌 때.  
  
-   **RBN_HEIGHTCHANGE** 높이가 변경 될 때 rebar 컨트롤에서 보냅니다.  
  
-   **RBN_LAYOUTCHANGED** 사용자 컨트롤의 밴드 레이아웃을 변경할 때 rebar 컨트롤에서 보냅니다.  
  
 이러한 알림에 대 한 자세한 내용은 참조 하십시오. [Rebar 컨트롤 참조](http://msdn.microsoft.com/library/windows/desktop/bb774375) Windows sdk에서입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CReBarCtrl 사용](../mfc/using-crebarctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

