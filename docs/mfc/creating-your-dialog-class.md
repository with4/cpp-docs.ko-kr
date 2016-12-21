---
title: "대화 상자 클래스 만들기 | Microsoft Docs"
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
  - "대화 상자[C++], 만들기"
  - "대화 상자 클래스, 클래스 추가 마법사"
  - "대화 상자 클래스, 만들기"
  - "파일[C++], 만들기"
  - "MFC 대화 상자, 만들기"
ms.assetid: d5321741-da41-47a8-bb1c-6a0e8b28c4c1
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 대화 상자 클래스 만들기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

For each dialog box in your program, create a new dialog class to work with the dialog resource.  
  
 [Adding a Class](../ide/adding-a-class-visual-cpp.md) explains how to create a new dialog class.  When you create a dialog class with the Add Class Wizard, it writes the following items in the .H and .CPP files you specify:  
  
 In the .H file:  
  
-   A class declaration for the dialog class.  The class is derived from [CDialog](../mfc/reference/cdialog-class.md).  
  
 In the .CPP file:  
  
-   A message map for the class.  
  
-   A standard constructor for the dialog box.  
  
-   An override of the [DoDataExchange](../Topic/CWnd::DoDataExchange.md) member function.  Edit this function.  It is used for dialog data exchange and validation capabilities as described later in [Dialog data exchange and validation](../mfc/dialog-data-exchange-and-validation.md).  
  
## 참고 항목  
 [코드 마법사로 대화 상자 클래스 만들기](../mfc/creating-a-dialog-class-with-code-wizards.md)   
 [대화 상자의 수명 주기](../mfc/life-cycle-of-a-dialog-box.md)