---
title: "&lt;system_error&gt; | Microsoft Docs"
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
  - "std.<system_error>"
  - "std::<system_error>"
  - "<system_error>"
  - "system_error"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "system_error 헤더"
ms.assetid: 5e046c6e-48d9-4740-8c8a-05f3727c1215
caps.latest.revision: 15
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;system_error&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Include the header `<system_error>` to define the exception class `system_error` and related templates for processing low\-level system errors.  
  
## 구문  
  
```  
#include <system_error>  
```  
  
### 개체  
  
|||  
|-|-|  
|[generic\_category](../Topic/generic_category.md)|Represents the category for generic errors.|  
|[system\_category](../Topic/system_category.md)|Represents the category for errors caused by low\-level system overflows.|  
  
### 형식 정의  
  
|||  
|-|-|  
|[generic\_errno](../Topic/generic_errno.md)|A type that represents the enumeration that provides the symbolic names for all the error\-code macros defined by Posix in `<errno.h>`.|  
  
### 함수  
  
|||  
|-|-|  
|[make\_error\_code](../Topic/make_error_code.md)|`error_code` 개체를 만듭니다.|  
|[make\_error\_condition](../Topic/make_error_condition.md)|`error_condition` 개체를 만듭니다.|  
  
### 연산자  
  
|||  
|-|-|  
|[operator\=\=](../Topic/operator==%20\(%3Csystem_error%3E\).md)|Tests if the object on the left side of the operator is equal to the object on the right side.|  
|[operator\!\=](../Topic/operator!=%20\(%3Csystem_error%3E\).md)|Tests if the object on the left side of the operator is not equal to the object on the right side.|  
|[함수입니다.\<](../Topic/operator%3C%20\(%3Csystem_error%3E\).md)|Tests if an object is less than the object passed in for comparison.|  
  
### 열거형  
  
|||  
|-|-|  
|[errc](../Topic/errc%20Enumeration.md)|`<errno.h>` 에서 Posix에 의해 정의된 모든 코드 오류 매크로 대해 기호화 된 이름을 제공합니다   .|  
  
### Classes and Structs  
  
|||  
|-|-|  
|[error\_category](../standard-library/error-category-class.md)|Represents the abstract, common base for objects that describes a category of error codes.|  
|[error\_code](../standard-library/error-code-class.md)|Represents low\-level system errors that are implementation\-specific.|  
|[error\_condition](../standard-library/error-condition-class.md)|Represents user\-defined error codes.|  
|[is\_error\_code\_enum](../standard-library/is-error-code-enum-class.md)|Represents a type predicate that tests for the [error\_code 클래스](../standard-library/error-code-class.md) enumeration.|  
|[is\_error\_condition\_enum](../standard-library/is-error-condition-enum-class.md)|Represents a type predicate that tests for the [error\_condition 클래스](../standard-library/error-condition-class.md) enumeration.|  
|[system\_error](../standard-library/system-error-class.md)|Represents the base class for all exceptions thrown to report a low\-level system overflow.|  
  
## 요구 사항  
 **헤더** \<system\_error\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)