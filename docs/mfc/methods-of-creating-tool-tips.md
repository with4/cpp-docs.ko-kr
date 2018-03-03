---
title: "도구 설명을 만드는 방법 | Microsoft Docs"
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
- CToolTipCtrl class [MFC], creating tool tips
- tool tips [MFC], tool tip controls
- tool tips [MFC], creating
ms.assetid: b015e9f4-ddfb-49a4-a5a6-fa2d45e4d328
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c2d38bd76ff5c8d06daf474cf1c1dcc0286183bc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="methods-of-creating-tool-tips"></a>도구 설명을 만드는 방법
MFC는 세 가지 클래스를 만들고 관리 도구 설명 컨트롤을 제공: [CWnd](../mfc/reference/cwnd-class.md), [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md), [CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md) 및 [CMFCToolTipCtrl](../mfc/reference/cmfctooltipctrl-class.md). 이러한 클래스에 도구 설명 멤버 함수는 Windows 공용 컨트롤을 API를 래핑합니다. 클래스 `CToolBarCtrl` 및 클래스 `CToolTipCtrl` 클래스에서 파생 된 `CWnd`합니다.  
  
 `CWnd`만들기 및 관리 도구 설명 하는 4 개의 멤버 함수를 제공: [EnableToolTips](../mfc/reference/cwnd-class.md#enabletooltips), [CancelToolTips](../mfc/reference/cwnd-class.md#canceltooltips), [FilterToolTipMessage](../mfc/reference/cwnd-class.md#filtertooltipmessage), 및 [ OnToolHitTest](../mfc/reference/cwnd-class.md#ontoolhittest)합니다. 도구 설명 구현 하는 방법에 대 한 자세한 내용은 이러한 개별 멤버 함수를 참조 하십시오.  
  
 사용 하 여 도구 모음을 만드는 경우 `CToolBarCtrl`, 다음 멤버 함수를 사용 하 여 직접 해당 도구 모음에 대 한 도구 설명에 구현할 수 있습니다: [GetToolTips](../mfc/reference/ctoolbarctrl-class.md#gettooltips) 및 [SetToolTips](../mfc/reference/ctoolbarctrl-class.md#settooltips)합니다. 이러한 개별 멤버 함수 및 [도구 팁 알림 처리](../mfc/handling-tool-tip-notifications.md) 도구 설명 구현 하는 방법에 대 한 자세한 내용은 합니다.  
  
 `CToolTipCtrl` 클래스 Windows 공통 도구 설명 컨트롤의 기능을 제공 합니다. 단일 도구 설명 컨트롤 둘 이상의 도구에 대 한 정보를 제공할 수 있습니다. 한 도구는 어느 같은 창의 자식 창 또는 컨트롤 또는 창의 클라이언트 영역 내에서 응용 프로그램 정의 된 사각형 영역입니다. [CMFCToolTipCtrl](../mfc/reference/cmfctooltipctrl-class.md) 클래스에서 파생 `CToolTipCtrl` 비주얼 스타일을 추가 및 기능을 제공 하 고 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [CToolTipCtrl 사용](../mfc/using-ctooltipctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

