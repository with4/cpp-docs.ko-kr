---
title: "프레임워크의 대화 상자 구성 요소 | Microsoft Docs"
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
  - "대화 상자 클래스, 대화 상자 구성 요소"
  - "대화 상자 템플릿, MFC 프레임워크"
  - "MFC 대화 상자, MFC 대화 상자 정보"
  - "MFC 대화 상자, 만들기"
  - "MFC 대화 상자, 대화 상자 리소스"
ms.assetid: 592db160-0a8a-49be-ac72-ead278aca53f
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# 프레임워크의 대화 상자 구성 요소
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In the MFC framework, a dialog box has two components:  
  
-   A dialog\-template resource that specifies the dialog box's controls and their placement.  
  
     The dialog resource stores a dialog template from which Windows creates the dialog window and displays it.  The template specifies the dialog box's characteristics, including its size, location, style, and the types and positions of the dialog box's controls.  You will usually use a dialog template stored as a resource, but you can also create your own template in memory.  
  
-   A dialog class, derived from [CDialog](../mfc/reference/cdialog-class.md), to provide a programmatic interface for managing the dialog box.  
  
     A dialog box is a window and will be attached to a Windows window when visible.  When the dialog window is created, the dialog\-template resource is used as a template for creating child window controls for the dialog box.  
  
## 참고 항목  
 [대화 상자](../mfc/dialog-boxes.md)   
 [대화 상자의 수명 주기](../mfc/life-cycle-of-a-dialog-box.md)