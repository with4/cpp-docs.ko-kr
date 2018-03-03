---
title: "비활성 상태 중 마우스 상호 작용 제공 | Microsoft Docs"
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
- MFC ActiveX controls [MFC], mouse interaction
ms.assetid: b09106bf-44c7-4b9b-a6d9-0d624f16f5b3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a2f8991b6cc827c35c94b0989ef82e32422fd5c3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="providing-mouse-interaction-while-inactive"></a>비활성 상태 중 마우스 상호 작용 제공
컨트롤을 즉시 활성화 되지 않은 경우 계속 경우 처리할 수 `WM_SETCURSOR` 및 `WM_MOUSEMOVE` 컨트롤에 창이 자체의 경우에 메시지입니다. 이 사용 하 여 수행할 수 있습니다 `COleControl`의 구현의 `IPointerInactive` 인터페이스에는 기본적으로 해제 합니다. (참조는 *ActiveX SDK* 이 인터페이스의 설명에 대 한 합니다.) 를 사용 하려면 포함 된 `pointerInactive` 에서 반환 하는 플래그 집합에서 플래그 [COleControl::GetControlFlags](../mfc/reference/colecontrol-class.md#getcontrolflags):  
  
 [!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_1.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#10](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_2.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_3.cpp)]  
  
 선택 하는 경우이 플래그를 포함 하는 코드는 자동으로 생성 됩니다는 **마우스 포인터 알림 경우 비활성** 옵션에 [제어 설정](../mfc/reference/control-settings-mfc-activex-control-wizard.md) 는 와컨트롤을만들때페이지**MFC ActiveX 컨트롤 마법사**합니다.  
  
 경우는 `IPointerInactive` 인터페이스를 사용 하는 컨테이너 대리자 `WM_SETCURSOR` 및 `WM_MOUSEMOVE` 또한 메시지를 합니다. `COleControl`구현 `IPointerInactive` 조정 마우스 좌표를 적절히 후 컨트롤의 메시지 맵을 통해 메시지를 디스패치합니다. 해당 항목을 메시지 맵에 추가 하 여 일반적인 창 메시지와 마찬가지로 메시지를 처리할 수 있습니다. 이러한 메시지에 대 한 처리기를 사용 하지 않습니다는 `m_hWnd` 멤버 변수 (또는 모든 멤버 함수를 사용)이 아닌 값 아님을 **NULL**합니다.  
  
 비활성 컨트롤을 OLE 끌어서 놓기 작업의 대상으로 할 수 있습니다. 이 컨트롤의 창이 놓기 대상으로 등록할 수 있도록 사용자가을 통해 개체를 끌 순간에 컨트롤을 활성화 해야 합니다. 끄는 동안 되려면 활성화 되도록 재정의 [COleControl::GetActivationPolicy](../mfc/reference/colecontrol-class.md#getactivationpolicy)를 반환 하 고는 **POINTERINACTIVE_ACTIVATEONDRAG** 플래그:  
  
 [!code-cpp[NVC_MFC_AxOpt#11](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_4.cpp)]  
  
 사용 하도록 설정 된 `IPointerInactive` 인터페이스 일반적으로 의미 항상 마우스 메시지를 처리할 수 있어야 합니다. 지원 하지 않는 컨테이너에이 동작이 수행 될 수는 `IPointerInactive` 컨트롤이 표시 될 때 항상 활성화 해야 하는 인터페이스를 포함 해야 해당 컨트롤이 **OLEMISC_ACTIVATEWHENVISIBLE** 간에 플래그 기타 플래그입니다. 그러나이 플래그를 방지 하기 위해 적용 되는 데는 컨테이너에 있는 ö ¿ø `IPointerInactive`를 지정할 수도 있습니다는 **OLEMISC_IGNOREACTIVATEWHENVISIBLE** 플래그:  
  
 [!code-cpp[NVC_MFC_AxOpt#12](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_5.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [MFC ActiveX 컨트롤: 최적화](../mfc/mfc-activex-controls-optimization.md)

