---
title: "SDI 및 MDI | Microsoft Docs"
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
  - "프레임 창, MDI 응용 프로그램"
  - "프레임 창, SDI 응용 프로그램"
  - "MDI, SDI와 비교"
  - "MFC, windows"
  - "SDI(단일 문서 인터페이스), 응용 프로그램"
ms.assetid: bb7239d9-4759-4f63-bfff-44a04b48c067
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# SDI 및 MDI
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC makes it easy to work with both single\-document interface \(SDI\) and multiple\-document interface \(MDI\) applications.  
  
 SDI applications allow only one open document frame window at a time.  MDI applications allow multiple document frame windows to be open in the same instance of an application.  An MDI application has a window within which multiple MDI child windows, which are frame windows themselves, can be opened, each containing a separate document.  In some applications, the child windows can be of different types, such as chart windows and spreadsheet windows.  In that case, the menu bar can change as MDI child windows of different types are activated.  
  
> [!NOTE]
>  Under Windows 95 and later, applications are commonly SDI because the operating system has adopted a "document\-centered" view.  
  
 For more information, see [Documents, Views, and the Framework](../mfc/documents-views-and-the-framework.md).  
  
## 참고 항목  
 [클래스를 사용하여 Windows 응용 프로그램 작성](../mfc/using-the-classes-to-write-applications-for-windows.md)