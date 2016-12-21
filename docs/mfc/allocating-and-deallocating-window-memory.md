---
title: "창 메모리 할당 및 할당 취소 | Microsoft Docs"
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
  - "메모리 할당, 창 개체"
  - "메모리 할당 해제"
  - "메모리 할당 해제, 창 메모리"
  - "창 개체 저장소"
  - "창 개체 저장소, 할당"
  - "창 개체, 메모리 할당 해제"
ms.assetid: 7c962539-8461-4846-b5ca-fe3b15c313dc
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 창 메모리 할당 및 할당 취소
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Do not use the C\+\+ **delete** operator to destroy a frame window or view.  Instead, call the `CWnd` member function `DestroyWindow`.  Frame windows, therefore, should be allocated on the heap with operator **new**.  Be careful when allocating frame windows on the stack frame or globally.  Other windows should be allocated on the stack frame whenever possible.  
  
## 추가 정보  
  
-   [Creating windows](../mfc/creating-windows.md)  
  
-   [Window destruction sequence](../mfc/window-destruction-sequence.md)  
  
-   [Detaching a CWnd from its HWND](../mfc/detaching-a-cwnd-from-its-hwnd.md)  
  
## 참고 항목  
 [창 개체 소멸시키기](../mfc/destroying-window-objects.md)