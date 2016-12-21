---
title: "cancellation_token_source 클래스 | Microsoft Docs"
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
  - "pplcancellation_token/concurrency::cancellation_token_source"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cancellation_token_source 클래스"
ms.assetid: 3548b1a0-12b0-4334-95db-4bf57141c066
caps.latest.revision: 10
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# cancellation_token_source 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`cancellation_token_source` 클래스는 일부 취소 가능한 작업을 취소하는 기능을 나타냅니다.  
  
## 구문  
  
```  
class cancellation_token_source;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[cancellation\_token\_source::cancellation\_token\_source 생성자](../Topic/cancellation_token_source::cancellation_token_source%20Constructor.md)|오버로드됨.  새 `cancellation_token_source`를 생성합니다.  소스는 일부 취소할 수 있는 작업의 취소 플래그를 설정하는 데 사용할 수 있습니다.|  
|[cancellation\_token\_source::~cancellation\_token\_source 소멸자](../Topic/cancellation_token_source::~cancellation_token_source%20Destructor.md)||  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[cancellation\_token\_source::cancel 메서드](../Topic/cancellation_token_source::cancel%20Method.md)|토큰을 취소합니다.  토큰을 이용하는 `task_group`, `structured_task_group` 또는 `task`는 이 호출 시 취소되며 다음 중단점에서 예외를 throw합니다.|  
|[cancellation\_token\_source::create\_linked\_source 메서드](../Topic/cancellation_token_source::create_linked_source%20Method.md)|오버로드됨.  제공된 토큰이 취소된 경우 취소되는 `cancellation_token_source`를 만듭니다.|  
|[cancellation\_token\_source::get\_token 메서드](../Topic/cancellation_token_source::get_token%20Method.md)|이 소스와 연결된 취소 토큰을 반환합니다.  반환된 토큰은 취소를 폴링하거나 취소가 발생할 경우 콜백을 제공할 수 있습니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[cancellation\_token\_source::operator\!\= 연산자](../Topic/cancellation_token_source::operator!=%20Operator.md)||  
|[cancellation\_token\_source::operator\= 연산자](../Topic/cancellation_token_source::operator=%20Operator.md)||  
|[cancellation\_token\_source::operator\=\= 연산자](../Topic/cancellation_token_source::operator==%20Operator.md)||  
  
## 상속 계층  
 `cancellation_token_source`  
  
## 요구 사항  
 **헤더:** pplcancellation\_token.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)