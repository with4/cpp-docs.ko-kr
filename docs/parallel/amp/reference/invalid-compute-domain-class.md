---
title: "invalid_compute_domain 클래스 | Microsoft Docs"
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
  - "amprt/Concurrency::invalid_compute_domain"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "invalid_compute_domain 클래스"
ms.assetid: ac7a7166-8bdb-4db1-8caf-ea129ab5117e
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# invalid_compute_domain 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

런타임에서 [parallel\_for\_each](../Topic/parallel_for_each%20Function%20\(C++%20AMP\).md) 호출 사이트에서 지정된 계산 도메인을 사용하여 커널을 시작할 수 없는 경우 발생하는 예외입니다.  
  
## 구문  
  
```  
class invalid_compute_domain : public runtime_exception;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[invalid\_compute\_domain::invalid\_compute\_domain 생성자](../Topic/invalid_compute_domain::invalid_compute_domain%20Constructor.md)|`invalid_compute_domain` 클래스의 새 인스턴스를 초기화합니다.|  
  
## 상속 계층  
 `exception`  
  
 `runtime_exception`  
  
 `invalid_compute_domain`  
  
## 요구 사항  
 **헤더:** amprt.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [Concurrency 네임스페이스\(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)