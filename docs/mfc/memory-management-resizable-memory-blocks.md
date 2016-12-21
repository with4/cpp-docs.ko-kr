---
title: "메모리 관리: 크기 조정 가능한 메모리 블록 | Microsoft Docs"
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
  - "블록, 메모리 할당"
  - "메모리 할당, 메모리 블록 크기"
  - "메모리 블록, 할당"
  - "메모리 블록, 크기 조정 가능"
  - "메모리, 손상"
  - "크기 조정 가능한 메모리 블록"
ms.assetid: f0efe6f4-a3ed-4541-9195-51ec1291967a
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 메모리 관리: 크기 조정 가능한 메모리 블록
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The **new** and **delete** operators, described in the article [Memory Management: Examples](../mfc/memory-management-examples.md), are good for allocating and deallocating fixed\-size memory blocks and objects.  Occasionally, your application may need resizable memory blocks.  You must use the standard C run\-time library functions [malloc](../c-runtime-library/reference/malloc.md), [realloc](../c-runtime-library/reference/realloc.md), and [free](../c-runtime-library/reference/free.md) to manage resizable memory blocks on the heap.  
  
> [!IMPORTANT]
>  Mixing the **new** and **delete** operators with the resizable memory\-allocation functions on the same memory block will result in corrupted memory in the Debug version of MFC.  You should not use `realloc` on a memory block allocated with **new**.  Likewise, you should not allocate a memory block with the **new** operator and delete it with **free**, or use the **delete** operator on a block of memory allocated with `malloc`.  
  
## 참고 항목  
 [메모리 관리: 힙 할당](../mfc/memory-management-heap-allocation.md)