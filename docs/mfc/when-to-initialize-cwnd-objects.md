---
title: "CWnd 개체 초기화 시점 | Microsoft Docs"
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
  - "CWnd 개체, HWND 연결 시"
  - "CWnd 개체, 초기화 시점"
  - "HWND, CWnd 개체 연결 시"
  - "CWnd 개체 초기화"
  - "개체 초기화, CWnd"
  - "창 개체, CWnd 초기화 시점"
ms.assetid: 4d31bcb1-73db-4f2f-b71c-89b087569a10
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# CWnd 개체 초기화 시점
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

You cannot create your own child windows or call any Windows API functions in the constructor of a `CWnd`\-derived object.  This is because the `HWND` for the `CWnd` object has not been created yet.  Most Windows\-specific initialization, such as adding child windows, must be done in an [OnCreate](../Topic/CWnd::OnCreate.md) message handler.  
  
## 추가 정보  
  
-   [Creating document frame windows](../mfc/creating-document-frame-windows.md)  
  
-   [Document\/view creation](../mfc/document-view-creation.md)  
  
## 참고 항목  
 [프레임 창 사용](../mfc/using-frame-windows.md)