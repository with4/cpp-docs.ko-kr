---
title: "_HAS_ITERATOR_DEBUGGING | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_HAS_ITERATOR_DEBUGGING"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_HAS_ITERATOR_DEBUGGING"
ms.assetid: 90077dbb-8a76-4963-83a6-29f4854007a8
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# _HAS_ITERATOR_DEBUGGING
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Defines whether the iterator debugging feature is enabled in a debug build.  By default, iterator debugging is enabled.  자세한 내용은 [Debug Iterator Support](../standard-library/debug-iterator-support.md)을 참조하십시오.  
  
> [!IMPORTANT]
>  Use `_ITERATOR_DEBUG_LEVEL` to control `_HAS_ITERATOR_DEBUGGING`.  자세한 내용은 [\_ITERATOR\_DEBUG\_LEVEL](../standard-library/iterator-debug-level.md)을 참조하십시오.  
  
## 설명  
 To enable iterator debugging in debug builds, set **\_HAS\_ITERATOR\_DEBUGGING** to 1:  
  
```  
#define _HAS_ITERATOR_DEBUGGING 1  
```  
  
 **\_HAS\_ITERATOR\_DEBUGGING** cannot be set to 1 in retail builds.  
  
 To disable iterator debugging in debug builds, set **\_HAS\_ITERATOR\_DEBUGGING** to 0:  
  
```  
#define _HAS_ITERATOR_DEBUGGING 0  
```  
  
## 참고 항목  
 [\_ITERATOR\_DEBUG\_LEVEL](../standard-library/iterator-debug-level.md)   
 [Debug Iterator Support](../standard-library/debug-iterator-support.md)   
 [Checked Iterators](../standard-library/checked-iterators.md)   
 [안전한 라이브러리: C\+\+ 표준 라이브러리](../standard-library/safe-libraries-cpp-standard-library.md)