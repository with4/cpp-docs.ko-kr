---
title: "대화 상자 모음 | Microsoft Docs"
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
  - "CDialogBar 클래스, 대화 상자 모음"
  - "컨트롤 막대, 대화 상자 모음"
  - "대화 상자 모음"
  - "대화 상자 모음, 대화 상자 모음 정보"
  - "MFC, 컨트롤 막대"
ms.assetid: 485c8055-6bb0-4051-8417-dd2971499321
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 대화 상자 모음
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

A dialog bar is a toolbar, a kind of [control bar](../mfc/control-bars.md) that can contain any kind of control.  Because it has the characteristics of a modeless dialog box, a [CDialogBar](../mfc/reference/cdialogbar-class.md) object provides a more powerful toolbar.  
  
 There are several key differences between a toolbar and a `CDialogBar` object.  A `CDialogBar` object is created from a dialog\-template resource, which you can create with the Visual C\+\+ dialog editor and which can contain any kind of Windows control.  The user can tab from control to control.  And you can specify an alignment style to align the dialog bar with any part of the parent frame window or even to leave it in place if the parent is resized.  The following figure shows a dialog bar with a variety of controls.  
  
 ![VC 대화 상자 막대](../mfc/media/vc378t1.png "vc378T1")  
A Dialog Bar  
  
 In other respects, working with a `CDialogBar` object is like working with a modeless dialog box.  Use the dialog editor to design and create the dialog resource.  
  
 One of the virtues of dialog bars is that they can include controls other than buttons.  
  
 While it is normal to derive your own dialog classes from `CDialog`, you do not typically derive your own class for a dialog bar.  Dialog bars are extensions to a main window and any dialog\-bar control\-notification messages, such as **BN\_CLICKED** or **EN\_CHANGE**, will be sent to the parent of the dialog bar, the main window.  
  
## 참고 항목  
 [사용자 인터페이스 요소](../mfc/user-interface-elements-mfc.md)   
 [샘플](../top/visual-cpp-samples.md)