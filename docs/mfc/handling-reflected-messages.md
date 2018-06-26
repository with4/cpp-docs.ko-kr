---
title: 리플렉션된 메시지 처리 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- message handling [MFC], reflected messages
- reflected messages, handling
ms.assetid: 147a4e0c-51cc-4447-a8e1-c28b4cece578
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9b317f4c1b55e04f61aa0639bbd6953e5f36187a
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36931842"
---
# <a name="handling-reflected-messages"></a>리플렉션된 메시지 처리
반사를 사용 하면 같은 컨트롤에 대 한 메시지를 처리 하는 메시지 **WM_CTLCOLOR**, **WM_COMMAND**, 및 **WM_NOTIFY**, 컨트롤 자체 내에서. 그러면 컨트롤의 독립성 및 이식성이 향상됩니다. 이 메커니즘은 Windows 공용 컨트롤 및 ActiveX 컨트롤(이전의 OLE 컨트롤)에서 작동합니다.  
  
 메시지 리플렉션을 사용하면 `CWnd` 파생 클래스를 보다 쉽게 재사용할 수 있습니다. 메시지 리플렉션 작동 [cwnd:: Onchildnotify](../mfc/reference/cwnd-class.md#onchildnotify)를 사용 하 여 특별 한 **ON_XXX_REFLECT** 메시지 맵 항목: 예를 들어 **ON_CTLCOLOR_REFLECT** 및 **ON_CONTROL_REFLECT**합니다. [Technical Note 62](../mfc/tn062-message-reflection-for-windows-controls.md) 메시지 리플렉션 보다 자세히 설명 합니다.  
  
## <a name="what-do-you-want-to-do"></a>뭘 하고 싶으세요  
  
-   [메시지 리플렉션에 대 한 자세한 정보](../mfc/tn062-message-reflection-for-windows-controls.md)  
  
-   [공용 컨트롤에 대 한 메시지 리플렉션 구현](../mfc/tn062-message-reflection-for-windows-controls.md)  
  
-   [ActiveX 컨트롤에 대 한 메시지 리플렉션 구현](../mfc/mfc-activex-controls-subclassing-a-windows-control.md)  
  
## <a name="see-also"></a>참고 항목  
 [메시지 처리기 함수 선언](../mfc/declaring-message-handler-functions.md)
