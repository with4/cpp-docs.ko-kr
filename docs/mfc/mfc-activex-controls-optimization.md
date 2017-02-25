---
title: "MFC ActiveX 컨트롤: 최적화 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "장치 컨텍스트, 잘리지 않는 MFC ActiveX 컨트롤"
  - "깜빡임 없는 ActiveX 컨트롤"
  - "MFC ActiveX 컨트롤, 활성/비활성 상태"
  - "MFC ActiveX 컨트롤, 깜빡임 없는"
  - "MFC ActiveX 컨트롤, 마우스 상호 작용"
  - "MFC ActiveX 컨트롤, 최적화"
  - "MFC ActiveX 컨트롤, 창 없는"
  - "최적화, ActiveX 컨트롤"
  - "성능 최적화, ActiveX 컨트롤"
  - "성능, ActiveX 컨트롤"
  - "창 없는 MFC ActiveX 컨트롤"
ms.assetid: 8b11f26a-190d-469b-b594-5336094a0109
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# MFC ActiveX 컨트롤: 최적화
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

This article explains techniques you can use to optimize your ActiveX controls for better performance.  
  
 The topics [Turning Off the Activate When Visible Option](../mfc/turning-off-the-activate-when-visible-option.md) and [Providing Mouse Interaction While Inactive](../mfc/providing-mouse-interaction-while-inactive.md) discuss controls that don't create a window until activated.  The topic [Providing Windowless Activation](../mfc/providing-windowless-activation.md) discusses controls that never create a window, even when they are activated.  
  
 Windows have two major drawbacks for OLE objects: they prevent objects from being transparent or nonrectangular when active, and they add a large overhead to the instantiation and display of controls.  Typically, creating a window takes 60 percent of a control's creation time.  With a single shared window \(usually the container's\) and some dispatching code, a control receives the same window services, generally without a loss of performance.  Having a window is mostly unnecessary overhead for the object.  
  
 Some optimizations do not necessarily improve performance when your control is used in certain containers.  For example, containers released prior to 1996 did not support windowless activation, so implementing this feature will not provide a benefit in older containers.  However, nearly every container supports persistence, so optimizing your control's persistence code will likely improve its performance in any container.  If your control is specifically intended to be used with one particular type of container, you may want to research which of these optimizations is supported by that container.  In general, however, you should try to implement as many of these techniques as are applicable to your particular control to ensure your control performs as well as it possibly can in a wide array of containers.  
  
 You can implement many of these optimizations through the [MFC ActiveX Control Wizard](../mfc/reference/mfc-activex-control-wizard.md), on the [Control Settings](../mfc/reference/control-settings-mfc-activex-control-wizard.md) page.  
  
### MFC ActiveX Control Wizard OLE Optimization Options  
  
|Control setting in the MFC ActiveX Control Wizard|작업|추가 정보|  
|-------------------------------------------------------|--------|-----------|  
|**Activate when visible** check box|Clear|[Turning Off the Activate When Visible Option](../mfc/turning-off-the-activate-when-visible-option.md)|  
|**Windowless activation** check box|Select|[Providing Windowless Activation](../mfc/providing-windowless-activation.md)|  
|**Unclipped device context** check box|Select|[Using an Unclipped Device Context](../mfc/using-an-unclipped-device-context.md)|  
|**Flicker\-free activation** check box|Select|[Providing Flicker\-Free Activation](../mfc/providing-flicker-free-activation.md)|  
|**Mouse pointer notifications when inactive** check box|Select|[Providing Mouse Interaction While Inactive](../mfc/providing-mouse-interaction-while-inactive.md)|  
|**Optimized drawing code** check box|Select|[Optimizing Control Drawing](../mfc/optimizing-control-drawing.md)|  
  
 For detailed information about the member functions that implement these optimizations, see [COleControl](../mfc/reference/colecontrol-class.md).  The member functions are listed by use, such as [Windowless Operations](http://msdn.microsoft.com/ko-kr/e9e28f79-9a70-4ae4-a5aa-b3e92f1904df) and [Inactive Pointer Handling Functions](http://msdn.microsoft.com/ko-kr/e9e28f79-9a70-4ae4-a5aa-b3e92f1904df).  
  
 자세한 내용은 다음을 참조하십시오.  
  
-   [Optimizing Persistence and Initialization](../mfc/optimizing-persistence-and-initialization.md)  
  
-   [Providing Windowless Activation](../mfc/providing-windowless-activation.md)  
  
-   [Turning Off the Activate When Visible Option](../mfc/turning-off-the-activate-when-visible-option.md)  
  
-   [Providing Mouse Interaction While Inactive](../mfc/providing-mouse-interaction-while-inactive.md)  
  
-   [Providing Flicker\-Free Activation](../mfc/providing-flicker-free-activation.md)  
  
-   [Using an Unclipped Device Context](../mfc/using-an-unclipped-device-context.md)  
  
-   [Optimizing Control Drawing](../mfc/optimizing-control-drawing.md)  
  
## 참고 항목  
 [MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)