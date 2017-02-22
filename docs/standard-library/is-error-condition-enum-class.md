---
title: "is_error_condition_enum 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::is_error_condition_enum"
  - "std.is_error_condition_enum"
  - "is_error_condition_enum"
  - "system_error/std::is_error_condition_enum"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_error_condition_enum 클래스"
ms.assetid: 752bb87a-c61c-4304-9254-5aaf228b59c0
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# is_error_condition_enum 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Represents a type predicate that tests for the [error\_condition](../standard-library/error-condition-class.md) enumeration.  
  
## 구문  
  
```  
template<_Enum>  
    class is_error_condition_enum;  
```  
  
## 설명  
 An instance of this [type predicate](../standard-library/type-traits.md) holds true if the type `_Enum` is an enumeration value suitable for storing in an object of type `error_condition`.  
  
 It is permissible to add specializations to this type for user\-defined types.  
  
## 요구 사항  
 **헤더** \<system\_error\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [\<system\_error\>](../standard-library/system-error.md)