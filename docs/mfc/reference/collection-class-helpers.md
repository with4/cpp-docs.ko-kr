---
title: "컬렉션 클래스 도우미 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros.classes"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "컬렉션 클래스, 도우미 함수"
  - "ConstructElements 함수"
  - "DestructElements 함수"
  - "도우미 함수 컬렉션 클래스"
  - "SerializeElements 함수"
ms.assetid: bc3a2368-9edd-4748-9e6a-13cba79517ca
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# 컬렉션 클래스 도우미
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

The collection classes `CMap`, `CList`, and `CArray` use templated global helper functions for such purposes as comparing, copying, and serializing elements.  As part of your implementation of classes based on `CMap`, `CList`, and `CArray`, you must override these functions as necessary with versions tailored to the type of data stored in your map, list, or array.  For information on overriding helper functions such as `SerializeElements`, see the article [Collections: How to Make a Type\-Safe Collection](../../mfc/how-to-make-a-type-safe-collection.md).  Note that **ConstructElements** and **DestructElements** have been deprecated.  
  
 The Microsoft Foundation Class Library provides the following global functions to help you customize your collection classes:  
  
### Collection Class Helpers  
  
|||  
|-|-|  
|[CompareElements](../Topic/CompareElements.md)|Indicates whether elements are the same.|  
|[CopyElements](../Topic/CopyElements.md)|Copies elements from one array to another.|  
|[DumpElements](../Topic/DumpElements.md)|Provides stream\-oriented diagnostic output.|  
|[HashKey](../Topic/HashKey.md)|Calculates a hash key.|  
|[SerializeElements](../Topic/SerializeElements.md)|Stores or retrieves elements to or from an archive.|  
  
## 참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)   
 [CMap Class](../../mfc/reference/cmap-class.md)   
 [CList Class](../../mfc/reference/clist-class.md)   
 [CArray Class](../../mfc/reference/carray-class.md)