---
title: "예외: 생성자의 예외 | Microsoft Docs"
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
  - "생성자[C++], 예외"
  - "예외, 생성자"
  - "예외 throw, 생성자"
ms.assetid: a78eae5a-5821-4b27-9478-1436320ed1e1
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# 예외: 생성자의 예외
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

When throwing an exception in a constructor, clean up whatever objects and memory allocations you have made prior to throwing the exception, as explained in [Exceptions: Throwing Exceptions from Your Own Functions](../mfc/exceptions-throwing-exceptions-from-your-own-functions.md).  
  
 When throwing an exception in a constructor, the memory for the object itself has already been allocated by the time the constructor is called.  So, the compiler will automatically deallocate the memory occupied by the object after the exception is thrown.  
  
 For more information, see [Exceptions: Freeing Objects in Exceptions](../mfc/exceptions-freeing-objects-in-exceptions.md).  
  
## 참고 항목  
 [예외 처리](../mfc/exception-handling-in-mfc.md)