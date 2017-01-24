---
title: "cancellation_token 클래스 | Microsoft Docs"
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
  - "pplcancellation_token/concurrency::cancellation_token"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cancellation_token 클래스"
ms.assetid: 2787df2b-e9d3-440e-bfd0-841a46a9835f
caps.latest.revision: 10
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# cancellation_token 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`cancellation_token` 클래스는 일부 작업을 취소하도록 요청되었는지 여부를 확인하는 기능을 나타냅니다.  지정된 토큰을 `task_group`, `structured_task_group` 또는 `task`와 연결하여 암시적 취소를 제공할 수 있습니다.  연결된 `cancellation_token_source`가 취소된 경우 취소를 폴링하거나 콜백을 등록할 수도 있습니다.  
  
## 구문  
  
```  
class cancellation_token;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[cancellation\_token::cancellation\_token 생성자](../Topic/cancellation_token::cancellation_token%20Constructor.md)||  
|[cancellation\_token::~cancellation\_token 소멸자](../Topic/cancellation_token::~cancellation_token%20Destructor.md)||  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[cancellation\_token::deregister\_callback 메서드](../Topic/cancellation_token::deregister_callback%20Method.md)|등록 시 반환된 `cancellation_token_registration` 개체를 기반으로 `register` 메서드를 통해 이전에 등록한 콜백을 제거합니다.|  
|[cancellation\_token::is\_cancelable 메서드](../Topic/cancellation_token::is_cancelable%20Method.md)|이 토큰을 취소할 수 있는지 여부를 나타내는 값을 반환합니다.|  
|[cancellation\_token::is\_canceled 메서드](../Topic/cancellation_token::is_canceled%20Method.md)|토큰이 취소된 경우 `true`를 반환합니다.|  
|[cancellation\_token::none 메서드](../Topic/cancellation_token::none%20Method.md)|취소에 영향을 받을 수 없는 취소 토큰을 반환합니다.|  
|[cancellation\_token::register\_callback 메서드](../Topic/cancellation_token::register_callback%20Method.md)|토큰에 콜백 함수를 등록합니다.  만약 토큰이 취소되면 콜백이 만들어집니다.  이 메서드가 호출된 시점에 토큰이 이미 취소된 경우, 동기적으로 즉시 콜백이 만들어집니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[cancellation\_token::operator\!\= 연산자](../Topic/cancellation_token::operator!=%20Operator.md)||  
|[cancellation\_token::operator\= 연산자](../Topic/cancellation_token::operator=%20Operator.md)||  
|[cancellation\_token::operator\=\= 연산자](../Topic/cancellation_token::operator==%20Operator.md)||  
  
## 상속 계층  
 `cancellation_token`  
  
## 요구 사항  
 **헤더:** pplcancellation\_token.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)