---
title: Rebar 컨트롤에서 알림 메시지 처리 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- RBN_ notification messages, description of
- CReBarCtrl class [MFC], notification messages sent by
- RBN_ notification messages [MFC]
- notifications [MFC], CReBarCtrl
ms.assetid: 40f43a60-0c18-4d8d-8fab-213a095624f9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9a1d42d129ab7b7d2e98ae1126b8f32f68b1f356
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36931829"
---
# <a name="processing-notification-messages-in-a-rebar-control"></a>Rebar 컨트롤에서 알림 메시지 처리
Rebar 컨트롤의 부모 클래스에서 만듭니다는 `OnChildNotify` 모든 rebar 컨트롤에 대해 switch 문 사용 하는 처리기 함수 (`CReBarCtrl`) 알림 메시지를 처리 합니다. 개체 변경 내용 삭제 rebar 밴드의 레이아웃 및 등 rebar 컨트롤에서 밴드 rebar 컨트롤 위로 끌 때 부모 창에 알림이 전송 됩니다.  
  
 Rebar 컨트롤 개체에 의해 다음 알림 메시지를 보낼 수 있습니다.  
  
-   (RBS_AUTOSIZE 스타일으로 만든) rebar 컨트롤에서 보냅니다. RBN_AUTOSIZE 때 rebar 자동 크기를 조정 합니다.  
  
-   RBN_BEGINDRAG 밴드를 끌기 시작할 때 rebar 컨트롤에서 보냅니다.  
  
-   RBN_CHILDSIZE rebar 컨트롤 밴드의 자식 창 크기를 조정할 때 보냅니다.  
  
-   RBN_DELETEDBAND rebar 컨트롤 밴드를 삭제 한 다음 보냅니다.  
  
-   RBN_DELETINGBAND rebar 컨트롤 밴드는 삭제 될 때 보냅니다.  
  
-   RBN_ENDDRAG는 사용자는 밴드 끌기를 멈추면 rebar 컨트롤에서 보냅니다.  
  
-   RBN_GETOBJECT (RBS_REGISTERDROP 스타일으로 만든) rebar 컨트롤에서 전송 개체는 밴드 컨트롤에서 위로 끌 때.  
  
-   RBN_HEIGHTCHANGE rebar 컨트롤 높이가 변경 될 때 보냅니다.  
  
-   RBN_LAYOUTCHANGED 사용자 컨트롤의 밴드 레이아웃을 변경할 때 rebar 컨트롤에서 보냅니다.  
  
 이러한 알림에 대 한 자세한 내용은 참조 하십시오. [Rebar 컨트롤 참조](http://msdn.microsoft.com/library/windows/desktop/bb774375) Windows sdk에서입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CReBarCtrl 사용](../mfc/using-crebarctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

