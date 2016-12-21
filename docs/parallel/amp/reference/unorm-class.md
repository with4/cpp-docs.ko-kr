---
title: "unorm 클래스 | Microsoft Docs"
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
  - "amp_short_vectors/Concurrency::graphics::unorm"
  - "amp/Concurrency::graphics::unorm"
dev_langs: 
  - "C++"
ms.assetid: bc30bd20-6452-4d5f-9158-3b11c4c16ed2
caps.latest.revision: 8
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# unorm 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

unorm 숫자를 표현합니다.  각 요소는 \[0.0f, 1.0f\]의 범위에 있는 부동 소수점 수입니다.  
  
## 구문  
  
```  
class unorm;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[unorm::unorm 생성자](../Topic/unorm::unorm%20Constructor.md)|오버로드됨.  기본 생성자입니다.  0.0f로 초기화 합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|unorm::operator\-\- 연산자||  
|unorm::operator 부동 소수점 연산자|변환 연산자.  unorm 숫자를 부동 소수점 값으로 변환합니다.|  
|unorm::operator\*\= 연산자||  
|unorm::operator\/\= 연산자||  
|unorm::operator\+\+ 연산자||  
|unorm::operator\+\= 연산자||  
|unorm::operator\= 연산자||  
|unorm::operator\-\= 연산자||  
  
## 상속 계층  
 `unorm`  
  
## 요구 사항  
 **헤더:** amp\_short\_vectors.h  
  
 **네임스페이스:** Concurrency::graphics  
  
## 참고 항목  
 [Concurrency::graphics 네임스페이스](../../../parallel/amp/reference/concurrency-graphics-namespace.md)