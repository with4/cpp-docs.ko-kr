---
title: "배열, 목록 및 맵에 대한 템플릿 클래스 | Microsoft Docs"
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
  - "vc.classes.template"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "배열[C++], 클래스"
  - "목록 클래스"
  - "맵 클래스"
  - "템플릿 클래스"
  - "템플릿 클래스, 배열/목록 및 맵"
ms.assetid: a8331c4b-068a-48f8-a629-b8449601e121
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 배열, 목록 및 맵에 대한 템플릿 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

These collection classes are templates whose parameters determine the types of the objects stored in the aggregates.  The `CArray`, `CMap`, and `CList` classes use global helper functions that must usually be customized.  For more information about these helper functions, see [Collection Class Helpers](../mfc/reference/collection-class-helpers.md).  The typed pointer classes are wrappers for other classes in the class library.  By using these wrappers, you enlist the compiler's type\-checking to help you avoid errors.  For more information on using these classes, see [Collections](../mfc/collections.md).  
  
 These classes provide templates you can use to create arrays, lists, and maps using any type you like.  
  
 [CArray](../mfc/reference/carray-class.md)  
 Template class for making arrays of arbitrary types.  
  
 [CList](../mfc/reference/clist-class.md)  
 Template class for making lists of arbitrary types.  
  
 [CMap](../mfc/reference/cmap-class.md)  
 Template class for making maps with arbitrary key and value types.  
  
 [CTypedPtrArray](../mfc/reference/ctypedptrarray-class.md)  
 Template class for type\-safe arrays of pointers.  
  
 [CTypedPtrList](../mfc/reference/ctypedptrlist-class.md)  
 Template class for type\-safe lists of pointers.  
  
 [CTypedPtrMap](../mfc/reference/ctypedptrmap-class.md)  
 Template class for type\-safe maps with pointers.  
  
## 참고 항목  
 [클래스 개요](../mfc/class-library-overview.md)