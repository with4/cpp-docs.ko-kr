---
title: "error_category 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::error_category"
  - "system_error/std::error_category"
  - "error_category"
  - "std.error_category"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "error_category 클래스"
ms.assetid: e0a71e14-852d-4905-acd6-5f8ed426706d
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# error_category 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

오류 코드의 범주를 설명 하는 개체에 대 한 추상, 공통 기본을 나타냅니다.  
  
## 구문  
  
```  
class error_category;  
```  
  
## 설명  
 두 개의 미리 정의 된 개체가 구현 `error_category`: [generic\_category](../Topic/generic_category.md) 및 [system\_category](../Topic/system_category.md)합니다.  
  
### TypeDefs  
  
|||  
|-|-|  
|[value\_type](../Topic/error_category::value_type.md)|저장 된 오류 코드 값을 나타내는 형식입니다.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[default\_error\_condition](../Topic/error_category::default_error_condition.md)|오류 조건 개체에 대 한 오류 코드 값을 저장합니다.|  
|[equivalent](../Topic/error_category::equivalent.md)|Error 개체를 동일한 지 여부를 지정 하는 값을 반환 합니다.|  
|[message](../Topic/error_category::message.md)|지정된 된 오류 코드의 이름을 반환합니다.|  
|[name](../Topic/error_category::name.md)|범주의 이름을 반환합니다.|  
  
### 연산자  
  
|||  
|-|-|  
|[연산자\=\=](../Topic/error_category::operator==.md)|같은지 테스트 `error_category` 개체입니다.|  
|[operator\!\=](../Topic/error_category::operator!=.md)|다른 지 테스트 `error_category` 개체입니다.|  
|[operator\<](../Topic/error_category::operator%3C.md)|테스트는 [error\_category](../standard-library/error-category-class.md) 개체는 보다 작은 `error_category` 비교를 위해 전달 된 개체입니다.|  
  
## 요구 사항  
 **헤더:** \<system\_error\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<system\_error\>](../standard-library/system-error.md)