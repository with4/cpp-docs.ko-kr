---
title: "메모리 관리: 힙 할당 | Microsoft Docs"
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
  - "delete 연산자, MFC 디버그에 사용"
  - "메모리 누수 탐지"
  - "힙 할당"
  - "힙 할당, 설명"
  - "메모리 할당, 힙 메모리"
  - "메모리 누수, 검색"
  - "메모리, 누수 탐지"
  - "new 연산자, MFC 디버그에 사용"
ms.assetid: a5d949c6-1b79-476e-9c66-513a558203d9
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 메모리 관리: 힙 할당
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The heap is reserved for the memory allocation needs of the program.  It is an area apart from the program code and the stack.  Typical C programs use the functions `malloc` and **free** to allocate and deallocate heap memory.  The Debug version of MFC provides modified versions of the C\+\+ built\-in operators **new** and **delete** to allocate and deallocate objects in heap memory.  
  
 When you use **new** and **delete** instead of `malloc` and **free**, you are able to take advantage of the class library's memory\-management debugging enhancements, which can be useful in detecting memory leaks.  When you build your program with the Release version of MFC, the standard versions of the **new** and **delete** operators provide an efficient way to allocate and deallocate memory \(the Release version of MFC does not provide modified versions of these operators\).  
  
 Note that the total size of objects allocated on the heap is limited only by your system's available virtual memory.  
  
## 참고 항목  
 [메모리 관리](../mfc/memory-management.md)