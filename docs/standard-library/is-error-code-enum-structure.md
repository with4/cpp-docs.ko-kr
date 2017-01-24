---
title: "is_error_code_enum 구조체 | Microsoft Docs"
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
  - "future/std::is_error_code_enum"
dev_langs: 
  - "C++"
ms.assetid: 84ae4b99-66d2-41ba-9b50-645fcbe14630
caps.latest.revision: 13
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_error_code_enum 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Specialization that indicates that [future\_errc](../Topic/future_errc%20Enumeration.md) is suitable for storing an [error\_code](../standard-library/error-code-class.md).  
  
## 구문  
  
```  
template<>  
struct is_error_code_enum<Future_errc> : public true_type;  
```  
  
## 요구 사항  
 **헤더:** future  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [\<future\>](../standard-library/future.md)