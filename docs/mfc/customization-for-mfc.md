---
title: "MFC에 대한 사용자 지정 | Microsoft Docs"
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
  - "사용자 지정, MFC 확장"
ms.assetid: 3b1b7532-8cc9-48dc-9bbe-7fd4060530b5
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# MFC에 대한 사용자 지정
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

This topic provides tips for customizing an MFC application.  
  
## General Customizations  
 You can save and load the state of your application to the registry.  When you enable this option, your application will load its initial state from the registry.  If you change the initial docking layout for your application, you will have to clear the registry data for your application.  Otherwise, the data in the registry will override any changes that you made to the initial layout.  
  
## Class\-Specific Customizations  
 Additional customization tips can be found in the following topics:  
  
-   [CBasePane Class](../mfc/reference/cbasepane-class.md)  
  
-   [CDockablePane Class](../mfc/reference/cdockablepane-class.md)  
  
-   [CDockingManager Class](../mfc/reference/cdockingmanager-class.md)  
  
-   [CMFCBaseTabCtrl Class](../mfc/reference/cmfcbasetabctrl-class.md)  
  
## Additional Customization Tips  
 [키보드 및 마우스 사용자 지정](../mfc/keyboard-and-mouse-customization.md)  
  
 [사용자 정의 형식](../mfc/user-defined-tools.md)  
  
## 참고 항목  
 [MFC 데스크톱 응용 프로그램](../mfc/mfc-desktop-applications.md)   
 [사용자 지정의 보안 의미](../mfc/security-implications-of-customization.md)