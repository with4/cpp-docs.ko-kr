---
title: "메모리 관리 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "메모리"
  - "메모리 할당"
  - "메모리 할당, MFC"
  - "메모리, 관리"
  - "MFC, 메모리 관리"
ms.assetid: 934ac81b-d630-4232-88e5-ea74f7187987
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 메모리 관리
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

This group of articles describes how to take advantage of the general\-purpose services of the Microsoft Foundation Class Library \(MFC\) related to memory management.  Memory allocation can be divided into two main categories: frame allocations and heap allocations.  
  
 One main difference between the two allocation techniques is that with frame allocation you typically work with the actual memory block itself, while with heap allocation you are always given a pointer to the memory block.  Another major difference between the two schemes is that frame objects are automatically deleted, while heap objects must be explicitly deleted by the programmer.  
  
 For non\-MFC information about memory management in programs for Windows, see [Memory Management](http://msdn.microsoft.com/library/windows/desktop/aa366779) in the [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
## 추가 정보  
  
-   [Frame allocation](../mfc/memory-management-frame-allocation.md)  
  
-   [Heap allocation](../mfc/memory-management-heap-allocation.md)  
  
-   [Allocating memory for an array](../mfc/memory-management-examples.md)  
  
-   [Deallocating memory for an array from the heap](../mfc/memory-management-examples.md)  
  
-   [Allocating memory for a data structure](../mfc/memory-management-examples.md)  
  
-   [Allocating memory for an object](../mfc/memory-management-examples.md)  
  
-   [Resizable memory blocks](../mfc/memory-management-resizable-memory-blocks.md)  
  
## 참고 항목  
 [개념](../mfc/mfc-concepts.md)   
 [일반 MFC 항목](../mfc/general-mfc-topics.md)