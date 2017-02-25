---
title: "norm 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amp_short_vectors/Concurrency::graphics::norm"
dev_langs: 
  - "C++"
ms.assetid: 73002f3d-c25e-4119-bcd3-4c46c9b6abf1
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# norm 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

표준 숫자를 표현합니다.  각 요소는 \[\-1.0f, 1.0f\]의 범위에 있는 부동 소수점 수입니다.  
  
## 구문  
  
```  
class norm;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[norm::norm 생성자](../Topic/norm::norm%20Constructor.md)|오버로드됨.  기본 생성자입니다.  0.0f로 초기화 합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|norm::operator\- 연산자||  
|norm::operator\-\- 연산자||  
|norm::operator 부동 소수점 연산자|변환 연산자.  표준 숫자를 부동 소수점 값으로 변환합니다.|  
|norm::operator\*\= 연산자||  
|norm::operator\/\= 연산자||  
|norm::operator\+\+ 연산자||  
|norm::operator\+\= 연산자||  
|norm::operator\= 연산자||  
|norm::operator\-\= 연산자||  
  
## 상속 계층  
 `norm`  
  
## 요구 사항  
 **헤더:** amp\_short\_vectors.h  
  
 **네임스페이스:** Concurrency::graphics  
  
## 참고 항목  
 [Concurrency::graphics 네임스페이스](../../../parallel/amp/reference/concurrency-graphics-namespace.md)