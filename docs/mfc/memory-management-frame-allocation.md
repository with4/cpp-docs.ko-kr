---
title: "메모리 관리: 프레임 할당 | Microsoft Docs"
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
  - "메모리 누수 탐지"
  - "프레임 할당"
  - "프레임 변수"
  - "프레임 변수, 자동 삭제"
  - "힙 할당, 프레임 할당과 비교"
  - "메모리 할당, 프레임"
  - "메모리 누수, 프레임에 개체 할당"
  - "메모리 누수, 검색"
  - "메모리 누수, 프레임 할당"
  - "메모리, 누수 탐지"
  - "메모리, 회수"
  - "메모리, 해제"
  - "범위, 프레임 변수"
  - "스택 프레임"
  - "변수, 프레임 변수"
ms.assetid: 945a211a-6f4f-4679-bb6a-b0f2a0d4a6c1
caps.latest.revision: 13
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 메모리 관리: 프레임 할당
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Allocation on the frame takes its name from the "stack frame" that is set up whenever a function is called.  The stack frame is an area of memory that temporarily holds the arguments to the function as well as any variables that are defined local to the function.  Frame variables are often called "automatic" variables because the compiler automatically allocates the space for them.  
  
 There are two key characteristics of frame allocations.  First, when you define a local variable, enough space is allocated on the stack frame to hold the entire variable, even if it is a large array or data structure.  Second, frame variables are automatically deleted when they go out of scope:  
  
 [!code-cpp[NVC_MFC_Utilities#10](../mfc/codesnippet/CPP/memory-management-frame-allocation_1.cpp)]  
  
 For local function variables, this scope transition happens when the function exits, but the scope of a frame variable can be smaller than a function if nested braces are used.  This automatic deletion of frame variables is very important.  In the case of simple primitive types \(such as `int` or **byte**\), arrays, or data structures, the automatic deletion simply reclaims the memory used by the variable.  Since the variable has gone out of scope, it cannot be accessed anyway.  In the case of C\+\+ objects, however, the process of automatic deletion is a bit more complicated.  
  
 When an object is defined as a frame variable, its constructor is automatically invoked at the point where the definition is encountered.  When the object goes out of scope, its destructor is automatically invoked before the memory for the object is reclaimed.  This automatic construction and destruction can be very handy, but you must be aware of the automatic calls, especially to the destructor.  
  
 The key advantage of allocating objects on the frame is that they are automatically deleted.  When you allocate your objects on the frame, you don't have to worry about forgotten objects causing memory leaks. \(For details on memory leaks, see the article [Detecting Memory Leaks in MFC](http://msdn.microsoft.com/ko-kr/29ee8909-96e9-4246-9332-d3a8aa8d4658).\) A disadvantage of frame allocation is that frame variables cannot be used outside their scope.  Another factor in choosing frame allocation versus heap allocation is that for large structures and objects, it is often better to use the heap instead of the stack for storage since stack space is often limited.  
  
## 참고 항목  
 [메모리 관리](../mfc/memory-management.md)