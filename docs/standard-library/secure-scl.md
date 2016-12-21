---
title: "_SECURE_SCL | Microsoft Docs"
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
  - "_SECURE_SCL"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_SECURE_SCL"
ms.assetid: 4ffbc788-cc12-4c6a-8cd7-490081675086
caps.latest.revision: 10
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _SECURE_SCL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Defines whether [Checked Iterators](../standard-library/checked-iterators.md) are enabled.  If defined as 1, unsafe iterator use causes a runtime error and the program is terminated.  If defined as 0, checked iterators are disabled.  In debug mode, the default value for **\_SECURE\_SCL** is 1, meaning checked iterators are enabled.  In release mode, the default value for `_SECURE_SCL` is 0.  
  
> [!IMPORTANT]
>  Use `_ITERATOR_DEBUG_LEVEL` to control `_SECURE_SCL`.  자세한 내용은 [\_ITERATOR\_DEBUG\_LEVEL](../standard-library/iterator-debug-level.md)을 참조하십시오.  
  
## 설명  
 To enable checked iterators, set **\_SECURE\_SCL** to 1:  
  
```  
#define _SECURE_SCL 1  
```  
  
 To disable checked iterators, set **\_SECURE\_SCL** to 0:  
  
```  
#define _SECURE_SCL 0  
```  
  
 For information on how to disable warnings about checked iterators, see [\_SCL\_SECURE\_NO\_WARNINGS](../standard-library/scl-secure-no-warnings.md).  
  
## 참고 항목  
 [\_ITERATOR\_DEBUG\_LEVEL](../standard-library/iterator-debug-level.md)   
 [Checked Iterators](../standard-library/checked-iterators.md)   
 [Debug Iterator Support](../standard-library/debug-iterator-support.md)   
 [안전한 라이브러리: C\+\+ 표준 라이브러리](../standard-library/safe-libraries-cpp-standard-library.md)