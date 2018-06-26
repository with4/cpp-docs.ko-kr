---
title: 도구 설명 컨트롤 조작 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CToolTipCtrl class [MFC], manipulating tool tip attributes
- tool tips [MFC], attributes
ms.assetid: 3600afe5-712a-4b56-8456-96e85fe879af
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 91e2e247acb85188c1280713e9e5ad8ef8f19448
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929830"
---
# <a name="manipulating-the-tool-tip-control"></a>도구 설명 컨트롤 조작
클래스 `CToolTipCtrl` 멤버 그룹의 다양 한 특성을 제어 하는 함수를 제공는 `CToolTipCtrl` 개체 및 도구 설명 창이 있습니다.  
  
 초기, 팝업, 도구 설명 창이 설정에 대 한 호출을 사용 하 여 검색 하 고 기간을 reshow 및 [GetDelayTime](../mfc/reference/ctooltipctrl-class.md#getdelaytime) 및 [SetDelayTime](../mfc/reference/ctooltipctrl-class.md#setdelaytime)합니다.  
  
 다음 함수를 사용 하 여 도구 설명 창의 모양을 변경 합니다.  
  
-   [GetMargin](../mfc/reference/ctooltipctrl-class.md#getmargin) 및 [SetMargin](../mfc/reference/ctooltipctrl-class.md#setmargin) 도구 설명 테두리와 도구 사이의 너비 팁 텍스트를 검색 하 고 설정 합니다.  
  
-   [GetMaxTipWidth](../mfc/reference/ctooltipctrl-class.md#getmaxtipwidth) 및 [SetMaxTipWidth](../mfc/reference/ctooltipctrl-class.md#setmaxtipwidth) 최대 명령 단추의 도구 설명 창을 검색 하 고 설정 합니다.  
  
-   [GetTipBkColor](../mfc/reference/ctooltipctrl-class.md#gettipbkcolor) 및 [SetTipBkColor](../mfc/reference/ctooltipctrl-class.md#settipbkcolor) 배경색의 도구 설명 창을 검색 하 고 설정 합니다.  
  
-   [GetTipTextColor](../mfc/reference/ctooltipctrl-class.md#gettiptextcolor) 및 [SetTipTextColor](../mfc/reference/ctooltipctrl-class.md#settiptextcolor) 텍스트 색의 도구 설명 창을 검색 하 고 설정 합니다.  
  
 WM_LBUTTONXXX 메시지와 같은 중요 한 메시지에 대 한 알림을 도구 설명 컨트롤에 도구 설명 컨트롤에 메시지를 릴레이 해야 합니다. 이 릴레이 대 한 가장 좋은 방법은 호출을 수행 하는 것 [CToolTipCtrl::RelayEvent](../mfc/reference/ctooltipctrl-class.md#relayevent)에 `PreTranslateMessage` 소유자 창의 함수입니다. 다음 예제에서는 가능한 방법 중 하나 (도구 설명 컨트롤이 라고 할 `m_ToolTip`):  
  
 [!code-cpp[NVC_MFCControlLadenDialog#41](../mfc/codesnippet/cpp/manipulating-the-tool-tip-control_1.cpp)]  
  
 도구 설명 창이 즉시 제거 하려면 호출는 [팝](../mfc/reference/ctooltipctrl-class.md#pop) 멤버 함수입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CToolTipCtrl 사용](../mfc/using-ctooltipctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

