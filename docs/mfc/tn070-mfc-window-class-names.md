---
title: "TN070: MFC 창 클래스 이름 | Microsoft Docs"
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
  - "vc.mfc.classes"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "TN070"
  - "창 클래스 이름"
ms.assetid: 90617912-dd58-4a7c-9082-ced71736d7cd
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# TN070: MFC 창 클래스 이름
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다.  따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다.  최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.  
  
 MFC windows use a dynamically created class name that reflects the features of the window.  MFC generates class names dynamically for frame windows, views, and popup windows produced by the application.  Dialog boxes and controls produced by an MFC application have the Windows\-supplied name for the class of window in question.  
  
 You can replace the dynamically provided class name by registering your own window class and using it in an override of [PreCreateWindow](../Topic/CWnd::PreCreateWindow.md).  Their MFC\-supplied class names fit one of the two following forms:  
  
```  
Afx:%x:%x  
Afx:%x:%x:%x:%x:%x  
```  
  
 The hex digits that replace the `%x` characters are filled in from data from the [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) structure.  MFC uses this technique so that multiple C\+\+ classes requiring identical **WNDCLASS** structures can share the same registered window class.  Unlike most simple Win32 applications, MFC applications have only one **WNDPROC**, so you can easily share **WNDCLASS** structures to save time and memory.  The replaceable values for the `%x` characters shown above are as follows:  
  
-   **WNDCLASS.hInstance**  
  
-   **WNDCLASS.style**  
  
-   **WNDCLASS.hCursor**  
  
-   **WNDCLASS.hbrBackground**  
  
-   **WNDCLASS.hIcon**  
  
 The first form \(`Afx:%x:%x`\) is used when **hCursor**, **hbrBackground**, and **hIcon** are all **NULL**.  
  
## 참고 항목  
 [번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)   
 [범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)   
 [TN020: ID 명명 및 번호 매기기 규칙](../mfc/tn020-id-naming-and-numbering-conventions.md)