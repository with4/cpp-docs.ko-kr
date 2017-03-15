---
title: "ExitInstance 멤버 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CWinApp::ExitInstance"
  - "CWinApp.ExitInstance"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWinApp 클래스, ExitInstance"
  - "ExitInstance 메서드"
  - "프로그램[C++], 종료"
ms.assetid: 5bb597bd-8dab-4d49-8bcf-9c45aa8be4a2
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ExitInstance 멤버 함수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The [ExitInstance](../Topic/CWinApp::ExitInstance.md) member function of class [CWinApp](../mfc/reference/cwinapp-class.md) is called each time a copy of your application terminates, usually as a result of the user quitting the application.  
  
 Override `ExitInstance` if you need special cleanup processing, such as freeing graphics device interface \(GDI\) resources or deallocating memory used during program execution.  Cleanup of standard items such as documents and views, however, is provided by the framework, with other overridable functions for doing special cleanup specific to those objects.  
  
## 참고 항목  
 [CWinApp: 응용 프로그램 클래스](../mfc/cwinapp-the-application-class.md)