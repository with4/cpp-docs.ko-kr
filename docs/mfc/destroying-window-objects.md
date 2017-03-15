---
title: "창 개체 소멸시키기 | Microsoft Docs"
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
  - "프레임 창, 소멸"
  - "창 개체, 제거"
  - "창 개체, 소멸"
  - "창 개체, 제거"
ms.assetid: 3241fea0-c614-4a25-957d-20f21bd5fd0c
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# 창 개체 소멸시키기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Care must be taken with your own child windows to destroy the C\+\+ window object when the user is finished with the window.  If these objects are not destroyed, your application will not recover their memory.  Fortunately, the framework manages window destruction as well as creation for frame windows, views, and dialog boxes.  If you create additional windows, you are responsible for destroying them.  
  
## 추가 정보  
  
-   [Window destruction sequence](../mfc/window-destruction-sequence.md)  
  
-   [Allocating and deallocating window memory](../mfc/allocating-and-deallocating-window-memory.md)  
  
-   [Detaching a CWnd from its HWND](../mfc/detaching-a-cwnd-from-its-hwnd.md)  
  
-   [General Window Creation Sequence](../mfc/general-window-creation-sequence.md)  
  
-   [Destroying frame windows](../mfc/destroying-frame-windows.md)  
  
## 참고 항목  
 [창 개체](../mfc/window-objects.md)