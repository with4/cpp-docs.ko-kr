---
title: "CWinApp 및 MFC 응용 프로그램 마법사 | Microsoft Docs"
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
  - "CWinApp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "응용 프로그램 마법사[C++], 및 CWinApp"
  - "CWinApp 클래스, 및 MFC 응용 프로그램 마법사"
  - "MFC[C++], 마법사"
ms.assetid: f8ac0491-3302-4e46-981d-0790624eb8a2
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CWinApp 및 MFC 응용 프로그램 마법사
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

When it creates a skeleton application, the MFC Application Wizard declares an application class derived from [CWinApp](../mfc/reference/cwinapp-class.md).  The MFC Application Wizard also generates an implementation file that contains the following items:  
  
-   A message map for the application class.  
  
-   An empty class constructor.  
  
-   A variable that declares the one and only object of the class.  
  
-   A standard implementation of your `InitInstance` member function.  
  
 The application class is placed in the project header and main source files.  The names of the class and files created are based on the project name you supply in the MFC Application Wizard.  The easiest way to view the code for these classes is through [Class View](http://msdn.microsoft.com/ko-kr/8d7430a9-3e33-454c-a9e1-a85e3d2db925).  
  
 The standard implementations and message map supplied are adequate for many purposes, but you can modify them as needed.  The most interesting of these implementations is the `InitInstance` member function.  Typically, you will add code to the skeletal implementation of `InitInstance`.  
  
## 참고 항목  
 [CWinApp: 응용 프로그램 클래스](../mfc/cwinapp-the-application-class.md)   
 [재정의 가능 CWinApp 멤버 함수](../mfc/overridable-cwinapp-member-functions.md)   
 [특수 CWinApp 서비스](../mfc/special-cwinapp-services.md)