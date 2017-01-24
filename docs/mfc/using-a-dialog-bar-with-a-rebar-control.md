---
title: "대화 상자 모음과 Rebar 컨트롤 함께 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "WM_EX_TRANSPARENT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "대화 상자 모음, rebar 밴드와 사용"
  - "rebar 컨트롤, 대화 상자 모음"
  - "WS_EX_TRANSPARENT 스타일"
ms.assetid: e528cea0-6b81-4bdf-9643-7c03b6176590
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 대화 상자 모음과 Rebar 컨트롤 함께 사용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

As mentioned in [Rebar Controls and Bands](../mfc/rebar-controls-and-bands.md), each band can contain only one child window \(or control\).  This might be a limitation if you want to have more than one child window per band.  A convenient workaround is to create a dialog bar resource with multiple controls and then add a rebar band \(containing the dialog bar\) to the rebar control.  
  
 Normally, if you wanted the dialog bar band to appear transparent, you would set the **WS\_EX\_TRANSPARENT** extended style for the dialog bar object.  However, because **WS\_EX\_TRANSPARENT** has some issues with properly painting the background of a dialog bar, you will need to do a little extra work to achieve the desired effect.  
  
 The following procedure details the steps necessary to achieve transparency without using the **WS\_EX\_TRANSPARENT** extended style.  
  
### To implement a transparent dialog bar in a rebar band  
  
1.  Using the [Add Class dialog box](../mfc/reference/adding-an-mfc-class.md), add a new class \(for example, `CMyDlgBar`\) that implements your dialog bar object.  
  
2.  Add a handler for the `WM_ERASEBKGND` message.  
  
3.  In the new handler, modify the existing code to match the following example:  
  
     [!code-cpp[NVC_MFCControlLadenDialog#29](../mfc/codesnippet/CPP/using-a-dialog-bar-with-a-rebar-control_1.cpp)]  
  
4.  Add a handler for the `WM_MOVE` message.  
  
5.  In the new handler, modify the existing code to match the following example:  
  
     [!code-cpp[NVC_MFCControlLadenDialog#30](../mfc/codesnippet/CPP/using-a-dialog-bar-with-a-rebar-control_2.cpp)]  
  
 The new handlers simulate the transparency of the dialog bar by forwarding the `WM_ERASEBKGND` message to the parent window and forcing a repaint every time the dialog bar object is moved.  
  
## 참고 항목  
 [CReBarCtrl 사용](../mfc/using-crebarctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)