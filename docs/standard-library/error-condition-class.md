---
title: "error_condition 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "system_error/std::error_condition"
  - "std::error_condition"
  - "error_condition"
  - "std.error_condition"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "error_condition 클래스"
ms.assetid: 6690f481-97c9-4554-a0ff-851dc96b7a06
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# error_condition 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Represents user\-defined error codes.  
  
## 구문  
  
```  
class error_condition;  
```  
  
## 설명  
 An object of type `error_condition` stores an error code value and a pointer to an object that represents a [category](../standard-library/error-category-class.md) of error codes used for reported user\-defined errors.  
  
### 생성자  
  
|||  
|-|-|  
|[error\_condition](../Topic/error_condition::error_condition.md)|'`error_condition`' 형식의 개체를 생성합니다.|  
  
### 형식 정의  
  
|||  
|-|-|  
|[value\_type](../Topic/error_condition::value_type.md)|A type that represents the stored error code value.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[assign](../Topic/error_condition::assign.md)|Assigns an error code value and category to an error condition.|  
|[범주](../Topic/error_condition::category.md)|Returns the error category.|  
|[clear](../Topic/error_condition::clear.md)|Clears the error code value and category.|  
|[message](../Topic/error_condition::message.md)|Returns the name of the error code.|  
  
### 연산자  
  
|||  
|-|-|  
|[operator\=\=](../Topic/error_condition::operator==.md)|Tests for equality between `error_condition` objects.|  
|[operator\!\=](../Topic/error_condition::operator!=.md)|Tests for inequality between `error_condition` objects.|  
|[함수입니다.\<](../Topic/error_condition::operator%3C.md)|Tests if the `error_condition` object is less than the `error_code` object passed in for comparison.|  
|[operator\=](../Topic/error_condition::operator=.md)|Assigns a new enumeration value to the `error_condition` object.|  
|[operator bool](../Topic/error_condition::operator%20bool.md)|Casts a variable of type `error_condition`.|  
  
## 요구 사항  
 **헤더** \<system\_error\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [error\_category 클래스](../standard-library/error-category-class.md)   
 [\<system\_error\>](../standard-library/system-error.md)