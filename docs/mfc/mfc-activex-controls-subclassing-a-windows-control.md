---
title: "MFC ActiveX 컨트롤: Windows 컨트롤 서브클래싱 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- precreatewindow
- IsSubclassed
dev_langs:
- C++
helpviewer_keywords:
- OnDraw method, MFC ActiveX controls
- subclassing
- DoSuperclassPaint method [MFC]
- subclassing Windows controls
- subclassing, Windows controls
- reflected messages, in ActiveX controls
- PreCreateWindow method, overriding
- MFC ActiveX controls [MFC], subclassed controls
- MFC ActiveX controls [MFC], creating
- IsSubclassed method [MFC]
ms.assetid: 3236d4de-401f-49b7-918d-c84559ecc426
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3e41eefdf1c1be2d0e91061e0efce5f5408c1848
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-activex-controls-subclassing-a-windows-control"></a>MFC ActiveX 컨트롤: Windows 컨트롤 서브클래싱
이 문서에서는 ActiveX 컨트롤을 만드는 일반적인 Windows 컨트롤 서브클래싱에 대 한 프로세스를 설명 합니다. 컨트롤에 ActiveX 컨트롤을 개발 하는 빠른 방법을 기존 창을 서브클래싱 합니다. 새 컨트롤 그리기 및 마우스 클릭에 응답 같은 서브클래싱된 Windows 컨트롤의 기능을 갖게 됩니다. MFC ActiveX 컨트롤 샘플 [단추](../visual-cpp-samples.md) 은 Windows 컨트롤 서브클래싱의 예입니다.  
  
 Windows 컨트롤의 하위 클래스를 만들려면 다음 작업을 완료 합니다.  
  
-   [COleControl의 IsSubclassedControl 및 PreCreateWindow 멤버 함수를 재정의 합니다.](#_core_overriding_issubclassedcontrol_and_precreatewindow)  
  
-   [OnDraw 멤버 함수를 수정 합니다.](#_core_modifying_the_ondraw_member_function)  
  
-   [컨트롤에 반영 모든 ActiveX 컨트롤 메시지 OCM ()를 처리 합니다.](#_core_handling_reflected_window_messages)  
  
    > [!NOTE]
    >  이 작업의 대부분은가 수행 ActiveX 컨트롤 마법사를 사용 하 여 서브클래싱 할 컨트롤을 선택 하는 경우는 **부모 창 클래스 선택** 드롭 다운 목록에는 **제어 설정** 페이지.  
  
 컨트롤을 서브클래싱하에 자세한 내용은 기술 자료 문서 Q243454를 참조 합니다.  
  
##  <a name="_core_overriding_issubclassedcontrol_and_precreatewindow"></a>IsSubclassedControl 및 PreCreateWindow 재정의  
 재정의 하려면 `PreCreateWindow` 및 `IsSubclassedControl`, 다음 줄의 코드를 추가 `protected` 컨트롤 클래스 선언의 섹션:  
  
 [!code-cpp[NVC_MFC_AxSub#1](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_1.h)]  
  
 컨트롤 구현 파일에서 (합니다. CPP), 두 가지 재정의 기능을 구현 하는 코드의 다음 줄을 추가 합니다.  
  
 [!code-cpp[NVC_MFC_AxSub#2](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_2.cpp)]  
  
 공지,이 예제에서는 Windows 단추 컨트롤에 지정 된 `PreCreateWindow`합니다. 그러나 모든 표준 Windows 컨트롤 서브클래싱 할 수 있습니다. 표준 Windows 컨트롤에 대 한 자세한 내용은 참조 하십시오. [컨트롤](../mfc/controls-mfc.md)합니다.  
  
 Windows 컨트롤 서브클래싱, 특정 창 스타일을 지정 수 있습니다 (**WS_**) 또는 확장 창 스타일 (**WS_EX_**) 컨트롤의 창을 만들지 하는 데 사용할 플래그입니다. 이러한 매개 변수에 대해 값을 설정할 수는 `PreCreateWindow` 수정 하 여 멤버 함수는 **cs.style** 및 **cs.dwExStyle** 필드를 구성 합니다. 이 필드를 수정할 수 있어야 사용 하는 `OR` 클래스에 의해 설정 된 기본 플래그를 유지 하기 위해 작업 `COleControl`합니다. 예를 들어 컨트롤 단추 컨트롤을 서브클래싱하는 컨트롤을 확인란으로 표시 하려는 경우 다음 코드 줄에 삽입의 구현 `CSampleCtrl::PreCreateWindow`, return 문의 하기 전에:  
  
 [!code-cpp[NVC_MFC_AxSub#3](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_3.cpp)]  
  
 이 작업을 추가 **BS_CHECKBOX** 기본 스타일 플래그를 그대로 유지 하면서 플래그를 스타일 (**WS_CHILD**) 클래스의 `COleControl` 그대로 유지 합니다.  
  
##  <a name="_core_modifying_the_ondraw_member_function"></a>OnDraw 멤버 함수를 수정합니다.  
 서브클래싱된 컨트롤이 해당 Windows 컨트롤로 동일한 모양을 유지 하는 경우는 `OnDraw` 컨트롤에 대 한 멤버 함수를 호출 하기만 하면 있어야 합니다.는 `DoSuperclassPaint` 다음 예제와 같이 멤버 함수의 경우:  
  
 [!code-cpp[NVC_MFC_AxSub#4](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_4.cpp)]  
  
 `DoSuperclassPaint` 멤버 함수에 의해 구현 `COleControl`, Windows 컨트롤의 창 프로시저를 사용 하 여 지정 된 디바이스 컨텍스트 경계 사각형 내에서 컨트롤을 그리는 데 합니다. 이렇게 하면 컨트롤 표시 활성화 되지 않은 경우에 있습니다.  
  
> [!NOTE]
>  `DoSuperclassPaint` 멤버 함수는 장치 컨텍스트를 변수로 전달할 수 있도록 해당 컨트롤 형식 에서만 작동 합니다는 **wParam** 의 `WM_PAINT` 메시지입니다. 여기에 표준 Windows 컨트롤 중 일부와 같은 **스크롤 막대** 및 **단추**, 및의 모든 공용 컨트롤입니다. 이 동작을 지원 하지 않는 컨트롤에 대 한 비활성 컨트롤을 제대로 표시 하려면 코드를 제공 해야 합니다.  
  
##  <a name="_core_handling_reflected_window_messages"></a>리플렉션된 창 메시지 처리  
 일반적으로 Windows 컨트롤의 부모 창에 특정 한 창 메시지를 보냅니다. 와 같은 일부 프로젝트 메시지 **WM_COMMAND**, 사용자가 수행한 동작에 대 한 알림을 제공 합니다. 다른 사용자와 같은 `WM_CTLCOLOR`, 부모 창에서 정보를 받는 데 사용 됩니다. ActiveX 컨트롤은 일반적으로 다른 방법으로 부모 창와 통신합니다. 알림이 발생 하는 이벤트 (이벤트 알림 보내기)으로 전달 되 고 컨테이너의 앰비언트 속성에 액세스 하 여 컨트롤 컨테이너에 대 한 정보를 가져옵니다. 이러한 통신 기술을 존재 하기 때문에 ActiveX 컨트롤 컨테이너 컨트롤에서 보낸 모든 창 메시지 처리에 표시 되지 않습니다.  
  
 컨테이너는 서브클래싱된 Windows 컨트롤을 전송한 창 메시지를 받지 않도록 하려면 `COleControl` 컨트롤의 부모 역할을 하는 추가 창을 만듭니다. "Reflector" 라는 추가이 창은 서브 클래스는 Windows 컨트롤과 같은 크기와 위치에 컨트롤 창 있는 ActiveX 컨트롤에 대해서만 만들어집니다. 리플렉터 창은 특정 창 메시지를 차단 하 고 컨트롤에 다시 보냅니다. 그런 다음 해당 창 프로시저에서 컨트롤 (예: 이벤트 발생) ActiveX 컨트롤에 대 한 적절 한 작업을 수행 하 여 리플렉션된 메시지를 처리할 수 있습니다. 참조 [리플렉션된 창 메시지 Id](../mfc/reflected-window-message-ids.md) 가로챈 창의 목록을 메시지와 그에 해당 리플렉션된 메시지입니다.  
  
 ActiveX 컨트롤 컨테이너에 대 한 필요성을 제거 자체 메시지 리플렉션을 수행 되도록 디자인 됩니다 `COleControl` reflector 창과 런타임 서브클래싱된 Windows 컨트롤에 대 한 오버 헤드를 줄여 만들려고 합니다. `COleControl`컨테이너의 값을 갖는 MessageReflect 앰비언트 속성에 대 한 확인 하 여이 기능을 지원 하는지 여부를 검색 **TRUE**합니다.  
  
 리플렉션된 창 메시지를 처리 하려면 컨트롤 메시지 맵 항목을 추가 하 고 처리기 함수를 구현 합니다. 리플 렉 트 된 메시지 Windows에 의해 정의 된 메시지의 표준 집합의 일부가 되지 않으므로 클래스 뷰 이러한 메시지 처리기 추가 지원 하지 않습니다. 그러나 수동으로 처리기를 추가 하기 어렵지 않습니다.  
  
 추가 하려면 리플렉션된 창 메시지에 대 한 메시지 처리기 수동으로 다음을 수행 합니다.  
  
-   컨트롤 클래스에 해당 합니다. H 파일 처리기 함수를 선언 합니다. 함수 반환 형식이 있어야 합니다. **LRESULT** 및 두 개의 매개 변수 형식과 **WPARAM** 및 **LPARAM**각각. 예:  
  
     [!code-cpp[NVC_MFC_AxSub#5](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_5.h)]  
    [!code-cpp[NVC_MFC_AxSub#6](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_6.h)]  
  
-   컨트롤 클래스에 해당 합니다. CPP 파일에서 추가 된 `ON_MESSAGE` 메시지 맵에 항목입니다. 이 항목의 매개 변수는 메시지 식별자 및 처리기 함수의 이름 이어야 합니다. 예:  
  
     [!code-cpp[NVC_MFC_AxSub#7](../mfc/codesnippet/cpp/mfc-activex-controls-subclassing-a-windows-control_7.cpp)]  
  
-   또한는 합니다. CPP 파일 구현에서 **OnOcmCommand** 리플 렉 트 된 메시지를 처리할 멤버 함수입니다. **wParam** 및 **lParam** 매개 변수는 원래 창 메시지의와 동일 합니다.  
  
 MFC ActiveX 컨트롤 샘플을 참조 하는 메시지 처리 반영 하는 방법의 예로에 대 한 [단추](../visual-cpp-samples.md)합니다. 코드를 보여 줍니다는 **OnOcmCommand** 처리기를 감지 하 고 **BN_CLICKED** 알림 코드 발생 시켜 응답 (송신) Click 이벤트 및 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)

