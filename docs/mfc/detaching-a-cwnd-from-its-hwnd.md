---
title: "CWnd를 해당 HWND에서 분리 | Microsoft Docs"
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
  - "CWnd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWnd 개체, HWND에서 분리"
  - "Detach 메서드(CWnd 클래스)"
  - "HWND에서 CWnd 분리"
  - "HWND, CWnd 분리"
  - "CWnd에서 HWND 제거"
ms.assetid: 6efadf84-0517-4a3f-acfd-216e088f19c6
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CWnd를 해당 HWND에서 분리
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

If you need to circumvent the object\-`HWND` relationship, MFC provides another `CWnd` member function, [Detach](../Topic/CWnd::Detach.md), which disconnects the C\+\+ window object from the Windows window.  This prevents the destructor from destroying the Windows window when the object is destroyed.  
  
## 추가 정보  
  
-   [Creating windows](../mfc/creating-windows.md)  
  
-   [Window destruction sequence](../mfc/window-destruction-sequence.md)  
  
-   [Allocating and deallocating window memory](../mfc/allocating-and-deallocating-window-memory.md)  
  
## 참고 항목  
 [창 개체](../mfc/window-objects.md)