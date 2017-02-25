---
title: "error_code 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "error_code"
  - "std.error_code"
  - "std::error_code"
  - "system_error/std::error_code"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "error_code 클래스"
ms.assetid: c09b4a96-cb14-4281-a319-63543f9b2b4a
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# error_code 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Represents low\-level system errors that are implementation\-specific.  
  
## 구문  
  
```  
class error_code;  
```  
  
## 설명  
 An object of type `error_code` class stores an error code value and a pointer to an object that represents a [category](../standard-library/error-category-class.md) of error codes that describe reported low\-level system errors.  
  
### 생성자  
  
|||  
|-|-|  
|[error\_code](../Topic/error_code::error_code.md)|'`error_code`' 형식의 개체를 생성합니다.|  
  
### 형식 정의  
  
|||  
|-|-|  
|[value\_type](../Topic/error_code::value_type.md)|A type that represents the stored error code value.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[assign](../Topic/error_code::assign.md)|Assigns an error code value and category to an error code.|  
|[범주](../Topic/error_code::category.md)|Returns the error category.|  
|[clear](../Topic/error_code::clear.md)|Clears the error code value and category.|  
|[default\_error\_condition](../Topic/error_code::default_error_condition.md)|Returns the default error condition.|  
|[message](../Topic/error_code::message.md)|Returns the name of the error code.|  
  
### 연산자  
  
|||  
|-|-|  
|[operator\=\=](../Topic/error_code::operator==.md)|Tests for equality between `error_code` objects.|  
|[operator\!\=](../Topic/error_code::operator!=.md)|Tests for inequality between `error_code` objects.|  
|[함수입니다.\<](../Topic/error_code::operator%3C.md)|Tests if the `error_code` object is less than the `error_code` object passed in for comparison.|  
|[operator\=](../Topic/error_code::operator=.md)|Assigns a new enumeration value to the `error_code` object.|  
|[operator bool](../Topic/error_code::operator%20bool.md)|Casts a variable of type `error_code`.|  
  
## 요구 사항  
 **헤더** \<system\_error\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [error\_category 클래스](../standard-library/error-category-class.md)   
 [\<system\_error\>](../standard-library/system-error.md)