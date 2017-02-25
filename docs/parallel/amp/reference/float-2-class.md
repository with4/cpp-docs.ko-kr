---
title: "float_2 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amp_short_vectors/Concurrency::graphics::float_2::yx"
  - "amp_short_vectors/Concurrency::graphics::float_2::operator-="
  - "amp_short_vectors/Concurrency::graphics::float_2::operator++"
  - "amp_short_vectors/Concurrency::graphics::float_2::operator-"
  - "amp_short_vectors/Concurrency::graphics::float_2::r"
  - "amp_short_vectors/Concurrency::graphics::float_2::get_yx"
  - "amp_short_vectors/Concurrency::graphics::float_2::get_xy"
  - "amp_short_vectors/Concurrency::graphics::float_2::operator/="
  - "amp_short_vectors/Concurrency::graphics::float_2::set_yx"
  - "amp_short_vectors/Concurrency::graphics::float_2::x"
  - "amp_short_vectors/Concurrency::graphics::float_2::get_y"
  - "amp_short_vectors/Concurrency::graphics::float_2::operator+="
  - "amp_short_vectors/Concurrency::graphics::float_2::gr"
  - "amp_short_vectors/Concurrency::graphics::float_2::operator="
  - "amp_short_vectors/Concurrency::graphics::float_2::set_x"
  - "amp_short_vectors/Concurrency::graphics::float_2::operator--"
  - "amp_short_vectors/Concurrency::graphics::float_2::get_x"
  - "amp_short_vectors/Concurrency::graphics::float_2::operator*="
  - "amp_short_vectors/Concurrency::graphics::float_2::rg"
  - "amp_short_vectors/Concurrency::graphics::float_2::set_xy"
  - "amp_short_vectors/Concurrency::graphics::float_2::xy"
  - "amp_short_vectors/Concurrency::graphics::float_2"
  - "amp_short_vectors/Concurrency::graphics::float_2::set_y"
  - "amp_short_vectors/Concurrency::graphics::float_2::y"
  - "amp_short_vectors/Concurrency::graphics::float_2::g"
dev_langs: 
  - "C++"
ms.assetid: b3ebd48e-f8c8-4f00-a640-357f702f0cae
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# float_2 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

두 float형 실수의 짧은 벡터를 나타냅니다.  
  
## 구문  
  
```  
class float_2;  
```  
  
## 멤버  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|`value_type`||  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[float\_2::float\_2 생성자](../Topic/float_2::float_2%20Constructor.md)|오버로드됨.  기본 생성자는, 모든 요소를 0으로 초기화 합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|float\_2::get\_x 메서드||  
|float\_2::get\_xy 메서드||  
|float\_2::get\_y 메서드||  
|float\_2::get\_yx 메서드||  
|float\_2::ref\_g 메서드||  
|float\_2::ref\_r 메서드||  
|float\_2::ref\_x 메서드||  
|float\_2::ref\_y 메서드||  
|float\_2::set\_x 메서드||  
|float\_2::set\_xy 메서드||  
|float\_2::set\_y 메서드||  
|float\_2::set\_yx 메서드||  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|float\_2::operator\- 연산자||  
|float\_2::operator\-\- 연산자||  
|float\_2::operator\*\= 연산자||  
|float\_2::operator\/\= 연산자||  
|float\_2::operator\+\+ 연산자||  
|float\_2::operator\+\= 연산자||  
|float\_2::operator\= 연산자||  
|float\_2::operator\-\= 연산자||  
  
### 공용 상수  
  
|Name|설명|  
|----------|--------|  
|[float\_2::size 상수](../Topic/float_2::size%20Constant.md)||  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|float\_2::g 데이터 멤버||  
|float\_2::gr 데이터 멤버||  
|float\_2::r 데이터 멤버||  
|float\_2::rg 데이터 멤버||  
|float\_2::x 데이터 멤버||  
|float\_2::xy 데이터 멤버||  
|float\_2::y 데이터 멤버||  
|float\_2::yx 데이터 멤버||  
  
## 상속 계층  
 `float_2`  
  
## 요구 사항  
 **헤더:** amp\_short\_vectors.h  
  
 **네임스페이스:** Concurrency::graphics  
  
## 참고 항목  
 [Concurrency::graphics 네임스페이스](../../../parallel/amp/reference/concurrency-graphics-namespace.md)