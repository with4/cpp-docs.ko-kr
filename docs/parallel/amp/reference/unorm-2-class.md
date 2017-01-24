---
title: "unorm_2 클래스 | Microsoft Docs"
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
  - "amp_short_vectors/Concurrency::graphics::unnorm_2::operator+="
  - "amp_short_vectors/Concurrency::graphics::unnorm_2::y"
  - "amp_short_vectors/Concurrency::graphics::unnorm_2::set_y"
  - "amp_short_vectors/Concurrency::graphics::unnorm_2::x"
  - "amp_short_vectors/Concurrency::graphics::unnorm_2::get_yx"
  - "amp_short_vectors/Concurrency::graphics::unnorm_2::operator--"
  - "amp_short_vectors/Concurrency::graphics::unnorm_2::set_xy"
  - "amp_short_vectors/Concurrency::graphics::unnorm_2::operator*="
  - "amp_short_vectors/Concurrency::graphics::unnorm_2::xy"
  - "amp_short_vectors/Concurrency::graphics::unnorm_2::get_y"
  - "amp_short_vectors/Concurrency::graphics::unnorm_2::operator="
  - "amp_short_vectors/Concurrency::graphics::unnorm_2::set_x"
  - "amp_short_vectors/Concurrency::graphics::unnorm_2::rg"
  - "amp_short_vectors/Concurrency::graphics::unorm_2"
  - "amp_short_vectors/Concurrency::graphics::unnorm_2::operator-="
  - "amp_short_vectors/Concurrency::graphics::unnorm_2::operator/="
  - "amp_short_vectors/Concurrency::graphics::unnorm_2::get_xy"
  - "amp_short_vectors/Concurrency::graphics::unnorm_2::set_yx"
  - "amp_short_vectors/Concurrency::graphics::unnorm_2::yx"
  - "amp_short_vectors/Concurrency::graphics::unnorm_2::gr"
  - "amp_short_vectors/Concurrency::graphics::unnorm_2::r"
  - "amp_short_vectors/Concurrency::graphics::unnorm_2::operator-"
  - "amp_short_vectors/Concurrency::graphics::unnorm_2::get_x"
  - "amp_short_vectors/Concurrency::graphics::unnorm_2::g"
  - "amp_short_vectors/Concurrency::graphics::unnorm_2::operator++"
dev_langs: 
  - "C++"
ms.assetid: 62e88ea7-e29f-4f62-95ce-61a1f39f5e34
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# unorm_2 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

두 개의 부호 없는 일반 숫자의 짧은 벡터를 나타냅니다.  
  
## 구문  
  
```  
class unorm_2;  
```  
  
## 멤버  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|`value_type`||  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[unorm\_2::unorm\_2 생성자](../Topic/unorm_2::unorm_2%20Constructor.md)|오버로드됨.  기본 생성자는, 모든 요소를 0으로 초기화 합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|unorm\_2::get\_x 메서드||  
|unorm\_2::get\_xy 메서드||  
|unorm\_2::get\_y 메서드||  
|unorm\_2::get\_yx 메서드||  
|unorm\_2::ref\_g 메서드||  
|unorm\_2::ref\_r 메서드||  
|unorm\_2::ref\_x 메서드||  
|unorm\_2::ref\_y 메서드||  
|unorm\_2::set\_x 메서드||  
|unorm\_2::set\_xy 메서드||  
|unorm\_2::set\_y 메서드||  
|unorm\_2::set\_yx 메서드||  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|unorm\_2::operator\-\- 연산자||  
|unorm\_2::operator\*\= 연산자||  
|unorm\_2::operator\/\= 연산자||  
|unorm\_2::operator\+\+ 연산자||  
|unorm\_2::operator\+\= 연산자||  
|unorm\_2::operator\= 연산자||  
|unorm\_2::operator\-\= 연산자||  
  
### 공용 상수  
  
|Name|설명|  
|----------|--------|  
|unorm\_2::size 상수||  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|norm\_2::g 데이터 멤버||  
|unorm\_2::gr 데이터 멤버||  
|unorm\_2::r 데이터 멤버||  
|unorm\_2::rg 데이터 멤버||  
|unorm\_2::x 데이터 멤버||  
|unorm\_2::xy 데이터 멤버||  
|unorm\_2::y 데이터 멤버||  
|unorm\_2::yx 데이터 멤버||  
  
## 상속 계층  
 `unorm_2`  
  
## 요구 사항  
 **헤더:** amp\_short\_vectors.h  
  
 **네임스페이스:** Concurrency::graphics  
  
## 참고 항목  
 [Concurrency::graphics 네임스페이스](../../../parallel/amp/reference/concurrency-graphics-namespace.md)