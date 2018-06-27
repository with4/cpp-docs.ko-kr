---
title: CFrameWnd에서 파생 되지 않은 도구 설명 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- enabling tool tips [MFC]
- TOOLTIPTEXT structure [MFC]
- Help [MFC], tool tips for controls
- TTN_NEEDTEXT message [MFC]
- controls [MFC], tool tips
- handler functions [MFC], tool tips
ms.assetid: cad5ef0f-02e3-4151-ad0d-3d42e6932b0e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5f187ae7e3d5d9dbe6441aa8e2ba0f7631fd5072
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36956540"
---
# <a name="tool-tips-in-windows-not-derived-from-cframewnd"></a>CFrameWnd에서 파생되지 않은 창의 도구 설명
이 문서에서는 설명에서 파생 되지 않은 창에 포함 된 컨트롤에 대 한 도구 설명을 사용할 수 있도록 [CFrameWnd](../mfc/reference/cframewnd-class.md)합니다. 문서 [도구 모음 도구 설명](../mfc/toolbar-tool-tips.md) 컨트롤에 대 한 도구 설명에 대 한 정보를 제공는 `CFrameWnd`합니다.  
  
 이 문서에서는에서 다루는 항목은 다음과 같습니다.  
  
-   [도구 설명을 사용하도록 설정](../mfc/enabling-tool-tips.md)  
  
-   [도구 설명에 대한 TTN_NEEDTEXT 알림 처리](../mfc/handling-ttn-needtext-notification-for-tool-tips.md)  
  
-   [TOOLTIPTEXT 구조체](../mfc/tooltiptext-structure.md)  
  
 단추에 대 한 도구 설명을 자동으로 표시 되 고 부모 창에 포함 된 다른 컨트롤에서 파생 된 `CFrameWnd`합니다. ¿¡´ `CFrameWnd` 에 대 한 기본 처리기는 [TTN_GETDISPINFO](http://msdn.microsoft.com/library/windows/desktop/bb760269) 알림을 처리 하 **TTN_NEEDTEXT** 도구에서 보내는 알림 컨트롤 컨트롤과 관련 된 팁입니다.  
  
 그러나이 기본 처리기가 호출 되지 시기는 **TTN_NEEDTEXT** 없는 창에 컨트롤에 연결 된 도구 설명 컨트롤에서 알림이 전송 됩니다는 `CFrameWnd`, 대화 상자나 폼 보기를 컨트롤 처럼 합니다. 따라서에 대 한 처리기 함수를 제공 하는 데 필요한는 **TTN_NEEDTEXT** 자식 컨트롤에 대 한 도구 설명을 표시 하려면 알림 메시지입니다.  
  
 기본 도구 설명 하 여 창에 대해 제공 된 [CWnd::EnableToolTips](../mfc/reference/cwnd-class.md#enabletooltips) 연결 된 텍스트 필요가 없습니다. 표시할 도구 설명에 대 한 텍스트를 검색 하는 **TTN_NEEDTEXT** 도구 설명 창이 표시 되기 직전에 도구 설명 컨트롤의 부모 창에 알림이 전송 됩니다. 일부 값을 할당할이 메시지에 대 한 처리기가 없는 경우는 *pszText* 의 멤버는 **TOOLTIPTEXT** 구조, 텍스트가 도구 설명에 대해 표시 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [도구 설명](../mfc/tool-tips.md)

