---
title: "MFC ActiveX 컨트롤: 최적화 | Microsoft Docs"
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
- MFC ActiveX controls [MFC], windowless
- flicker-free ActiveX controls
- MFC ActiveX controls [MFC], mouse interaction
- device contexts, unclipped for MFC ActiveX controls
- MFC ActiveX controls [MFC], optimizing
- performance, ActiveX controls
- optimization, ActiveX controls
- MFC ActiveX controls [MFC], flicker-free
- windowless MFC ActiveX controls
- MFC ActiveX controls [MFC], active/inactive state
- optimizing performance, ActiveX controls
ms.assetid: 8b11f26a-190d-469b-b594-5336094a0109
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 46a17a6594db6c59148042f6e8c6cc72c7068dc0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-activex-controls-optimization"></a>MFC ActiveX 컨트롤: 최적화
이 문서에서는 기술을 더 나은 성능을 위해 ActiveX 컨트롤을 최적화 하기 위해 사용할 수 있습니다.  
  
 항목 [설정 Off the 되었을 때 활성화 표시 옵션](../mfc/turning-off-the-activate-when-visible-option.md) 및 [제공 마우스 상호 작용 하는 동안 비활성](../mfc/providing-mouse-interaction-while-inactive.md) 활성화 될 때까지 창을 만들지 컨트롤에 설명 합니다. 항목 [창 없는 활성화 제공](../mfc/providing-windowless-activation.md) 활성화 되는 경우에 한 창을 만들지 마십시오 하는 컨트롤에 설명 합니다.  
  
 창에는 OLE 개체에 대 한 두 가지 주요 단점: 개체의 경우를 더 큰 오버 헤드를 인스턴스화 및 컨트롤의 화면 표시에 추가 합니다. 일반적으로 창을 만드는 컨트롤의 생성 시간의 60%를 사용 합니다. 단일 공유 창 (일반적으로 컨테이너의) 및 디스패치 일부 코드를 사용 하 여 컨트롤 성능 손실 없이 일반적으로 동일한 창 서비스를 받습니다. 창 개체에 대 한 대부분 불필요 한 오버 헤드를 합니다.  
  
 특정 컨테이너에서 컨트롤을 사용할 경우 일부 최적화 성능이 반드시 향상 되지 않습니다. 예를 들어 컨테이너 1996 이전의 해제 되므로이 기능을 구현 해도 오래 된 컨테이너의 이점을 제공 하지 않습니다 창 없는 활성화를 지원 하지 않았습니다. 그러나 거의 모든 컨테이너 컨트롤의 지 속성 코드 최적화는 모든 컨테이너에서 성능을 향상 시킬 하므로 지 속성을 지원 합니다. 한 가지 특정 유형의 컨테이너에서 사용 되는 컨트롤을 사용 하려면 구체적으로, 하려는 알아보고 해당 컨테이너에서 지원 되는 이러한 최적화 합니다. 그러나 일반적으로 마십시오 다양 한 종류의 컨테이너에서 할 수 있는 다양 한 컨트롤 잘 작동할 수 있도록 특정 컨트롤에 적용할 수는 이러한 기법을 구현 합니다.  
  
 많은 이러한 최적화를 통해 구현할 수는 [MFC ActiveX 컨트롤 마법사](../mfc/reference/mfc-activex-control-wizard.md)의 [제어 설정](../mfc/reference/control-settings-mfc-activex-control-wizard.md) 페이지.  
  
### <a name="mfc-activex-control-wizard-ole-optimization-options"></a>MFC ActiveX 컨트롤 마법사 OLE 최적화 옵션  
  
|MFC ActiveX 컨트롤 마법사의 제어 설정|작업|추가 정보|  
|-------------------------------------------------------|------------|----------------------|  
|**표시 되었을 때 활성화** 확인란|지우기|[해제 된 되었을 때 활성화 표시 옵션](../mfc/turning-off-the-activate-when-visible-option.md)|  
|**창 없는 활성화** 확인란|선택|[창 없는 활성화 제공](../mfc/providing-windowless-activation.md)|  
|**잘리지 않는 장치 컨텍스트** 확인란|선택|[잘리지 않는 장치 컨텍스트 사용](../mfc/using-an-unclipped-device-context.md)|  
|**깜빡임 없는 활성화** 확인란|선택|[깜빡임 없는 활성화 제공](../mfc/providing-flicker-free-activation.md)|  
|**마우스 포인터 알림 비활성 상태일 때** 확인란|선택|[비활성 상태 중 마우스 상호 작용 제공](../mfc/providing-mouse-interaction-while-inactive.md)|  
|**그리기 코드 최적화** 확인란|선택|[컨트롤 그리기 최적화](../mfc/optimizing-control-drawing.md)|  
  
 이러한 최적화를 구현 하는 멤버 함수에 대 한 자세한 내용은 참조 하십시오. [COleControl](../mfc/reference/colecontrol-class.md)합니다. 멤버 함수를 사용 하 여 같은 나열 됩니다 [창 없는 작업](http://msdn.microsoft.com/en-us/e9e28f79-9a70-4ae4-a5aa-b3e92f1904df) 및 [비활성 포인터 처리 함수와](http://msdn.microsoft.com/en-us/e9e28f79-9a70-4ae4-a5aa-b3e92f1904df)합니다.  
  
 자세한 내용은 다음을 참조하세요.  
  
-   [지속성 및 초기화 최적화](../mfc/optimizing-persistence-and-initialization.md)  
  
-   [창 없는 활성화 제공](../mfc/providing-windowless-activation.md)  
  
-   [해제 된 되었을 때 활성화 표시 옵션](../mfc/turning-off-the-activate-when-visible-option.md)  
  
-   [비활성 상태 중 마우스 상호 작용 제공](../mfc/providing-mouse-interaction-while-inactive.md)  
  
-   [깜빡임 없는 활성화 제공](../mfc/providing-flicker-free-activation.md)  
  
-   [잘리지 않는 장치 컨텍스트 사용](../mfc/using-an-unclipped-device-context.md)  
  
-   [컨트롤 그리기 최적화](../mfc/optimizing-control-drawing.md)  
  
## <a name="see-also"></a>참고 항목  
 [MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)

