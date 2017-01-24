---
title: "cancellation_token_registration 클래스 | Microsoft Docs"
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
  - "pplcancellation_token/concurrency::cancellation_token_registration"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cancellation_token_registration 클래스"
ms.assetid: 823d63f4-7233-4d65-8976-6152ccf12d0e
caps.latest.revision: 9
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# cancellation_token_registration 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`cancellation_token_registration` 클래스는 `cancellation_token`의 콜백 알림을 나타냅니다.  취소 발생 시 알림을 받는 데 `cancellation_token`의 `register` 메서드를 사용하면 `deregister` 메서드 사용을 통해 더 이상 만들어지지 않는 특정 콜백을 호출자가 요청할 수 있도록 `cancellation_token_registration` 개체가 콜백에 대한 핸들로 반환됩니다.  
  
## 구문  
  
```  
class cancellation_token_registration;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[cancellation\_token\_registration::cancellation\_token\_registration 생성자](../Topic/cancellation_token_registration::cancellation_token_registration%20Constructor.md)||  
|[cancellation\_token\_registration::~cancellation\_token\_registration 소멸자](../Topic/cancellation_token_registration::~cancellation_token_registration%20Destructor.md)||  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[cancellation\_token\_registration::operator\!\= 연산자](../Topic/cancellation_token_registration::operator!=%20Operator.md)||  
|[cancellation\_token\_registration::operator\= 연산자](../Topic/cancellation_token_registration::operator=%20Operator.md)||  
|[cancellation\_token\_registration::operator\=\= 연산자](../Topic/cancellation_token_registration::operator==%20Operator.md)||  
  
## 상속 계층  
 `cancellation_token_registration`  
  
## 요구 사항  
 **헤더:** pplcancellation\_token.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)