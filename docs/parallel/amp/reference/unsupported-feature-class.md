---
title: "unsupported_feature 클래스 | Microsoft Docs"
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
  - "amprt/Concurrency::unsupported_feature"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "unsupported_feature 클래스"
ms.assetid: 6b1ab917-df13-48c7-9648-7cb2465a0ff5
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# unsupported_feature 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

지원되지 않는 기능이 사용될 때 throw되는 예외입니다.  
  
## 구문  
  
```  
class unsupported_feature : public runtime_exception;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[unsupported\_feature::unsupported\_feature 생성자](../Topic/unsupported_feature::unsupported_feature%20Constructor.md)|`unsupported_feature`의 새 인스턴스를 생성합니다.|  
  
## 상속 계층  
 `exception`  
  
 `runtime_exception`  
  
 `unsupported_feature`  
  
## 요구 사항  
 **헤더:** amprt.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [Concurrency 네임스페이스\(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)