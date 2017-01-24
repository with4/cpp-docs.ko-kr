---
title: "창 없는 활성화 제공 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "활성화[C++], MFC ActiveX 컨트롤"
  - "활성화[C++], 창 없는"
  - "MFC ActiveX 컨트롤[C++], 활성화 옵션"
  - "창 없는 MFC ActiveX 컨트롤 활성화"
ms.assetid: 094903b5-c344-42fa-96ff-ce01e16891c5
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 창 없는 활성화 제공
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

창 생성 코드는 실행하는데 비용이 많이 듭니다. \(그러므로 **CreateWindow** 를 호출 할때 발생합니다\)  스크린 창을 유지하는 컨트롤은 창에 대한 관리 메세지를 가집니다.  창이 없는 컨트롤은 창 컨트롤 보다 더 빠릅니다.  
  
 창 없는 컨트롤의 장점은 창 있는 컨트롤과 달리 투명한 그림 이나 사각형이 아닌 영역을 지원하는 것입니다.  투명한 컨트롤의 일반적인 에는 투명 배경을 사용한 텍스트 컨트롤입니다.  컨트롤은 텍스트는 그리지만 배경을 그리지 않습니다. 따라서 텍스트 아래 뭐가 있는 보여집니다.  새로움 형식은 가끔 원형 단추 및 화살표와 같은 사각형이 아닌 컨트롤의 사용을 만듭니다.  
  
 종종, 컨트롤은 개별 창이 필요하진 않습니다. 대신에 해당 컨테이너의 창 서비스를 이용할 수 있습니다. 또한 창이 없는 개체를 지원하기 위해 쓰여진 컨테이너를 제공합니다.  창 없는 컨트롤은 이전 버전과 호환 버전의 컨테이너입니다.  창 없는 컨트롤을 지원 하도록 작성 되지 않은 이전 버전의 컨테이너는 창 없는 컨트롤 창이 활성 상태인 경우를 만듭니다.  
  
 창 없는 컨트롤에는 자체 창이 없으므로 \(창을 가지는\) 컨테이너는 컨트롤의 창에서 서비스를 제공 합니다.  예를 들어, 컨트롤이 키보드 포커스 쿼리 마우스를 캡처하거나 디바이스 컨텍스트를 가져와야 하는 경우 이러한 작업은 컨테이너에 의해 관리 됩니다.  해당 창없는 컨트롤의 창으로 전송 컨테이너의 경로를 사용자가 `IOleInPlaceObjectWindowless` 을 사용하여 입력 한 메시지 \(이 인터페이스의 설명에 대해 *ActiveX SDK* 를 참조하십시오\) `COleControl` 멤버 함수는 컨테이너에서 이러한 서비스를 호출합니다.  
  
 컨트롤이 창 없는 활성화를 사용하게 하려면 [COleControl::GetControlFlags](../Topic/COleControl::GetControlFlags.md)가 반환하는 플래그의 집합에 **windowlessActivate**  플래그를 포함하십시오.  예를 들면 다음과 같습니다.  
  
 [!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/CPP/providing-windowless-activation_1.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#6](../mfc/codesnippet/CPP/providing-windowless-activation_2.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/CPP/providing-windowless-activation_3.cpp)]  
  
 MFC ActiveX\-Control 마법사의 [Control Settings](../mfc/reference/control-settings-mfc-activex-control-wizard.md) 페이지에서 **Windowless activation** 옵션을 선택한 경우, 플래그를 포함하는 코드는 자동적으로 생성됩니다.  
  
 창 없는 활성화가 사용가능하면, 컨테이너는 컨트롤의 `IOleInPlaceObjectWindowless` 인터페이스에 입력 메시지를 위임합니다.  `COleControl` 의 인터페이스의 구현은 조정 마우스 좌표를 적당히 마우스 조정을 적절히 조정한 후 컨트롤의 메시지 맵을 통해 메시지를 발송 합니다.  메시지 맵에 해당 엔트리를 추가 하여 메시지를 보통의 창 메시지 처럼 처리할 수 있습니다.  해당 값에 대한 첫 확인을 하지 않고 `m_hWnd`멤버 변수\(사용하는 멤버 함수\)를 사용하여 피한 이러한 메세지에 대한 처리기는 **NULL** 이 아닙니다.  
  
 `COleControl` 는 컨테이너에서 적절하게 마우스 캡쳐, 키보드 포커스, 스크롤 및 다른 창 서비스를 호출하는 멤버 함수를 제공합니다. 아래를 포함하여 :  
  
-   [GetFocus](../Topic/COleControl::GetFocus.md), [SetFocus](../Topic/COleControl::SetFocus.md)  
  
-   [GetCapture](../Topic/COleControl::GetCapture.md), [SetCapture](../Topic/COleControl::SetCapture.md), [ReleaseCapture](../Topic/COleControl::ReleaseCapture.md)  
  
-   [GetDC](../Topic/COleControl::GetDC.md), [ReleaseDC](../Topic/COleControl::ReleaseDC.md)  
  
-   [InvalidateRgn](../Topic/COleControl::InvalidateRgn.md)  
  
-   [ScrollWindow](../Topic/COleControl::ScrollWindow.md)  
  
-   [GetClientRect](../Topic/COleControl::GetClientRect.md)  
  
 창 없는 컨트롤에서, 해당 `CWnd` 멤버 함수 또는 관련된 Win32 API 함수 대신에  `COleControl` 멤버 함수를 사용해야 합니다.  
  
 창 없는 컨트롤에 OLE를 끌어서 놓기 작업의 대상으로 지정할 수 있습니다.  일반적으로 해당 컨트롤의 창을 끌어 놓기 대상으로 등록 해야 합니다.  컨트롤에는 자체의 창이 있으면 이후 컨테이너를 창 놓기 대상으로 사용 합니다.  컨트롤은 `IDropTarget`인터페이스의 구현을 적절한 시기에 컨테이너가 호출을 위임할 수 있도록 제공합니다.  컨테이너에 이 인터페이스를 노출하려면 [COleControl::GetWindowlessDropTarget](../Topic/COleControl::GetWindowlessDropTarget.md) 를 재정의하십시오.  예를 들면 다음과 같습니다.  
  
 [!code-cpp[NVC_MFC_AxOpt#8](../mfc/codesnippet/CPP/providing-windowless-activation_4.cpp)]  
  
## 참고 항목  
 [MFC ActiveX 컨트롤: 최적화](../mfc/mfc-activex-controls-optimization.md)