---
title: "completion_future 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amprt/Concurrency::completion_future"
dev_langs: 
  - "C++"
ms.assetid: 1303c62e-546d-4b02-a578-251ed3fc0b6b
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# completion_future 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

C\+\+ AMP 비동기 작업에 상응하는 이후를 나타냅니다.  
  
## 구문  
  
```  
class completion_future;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[completion\_future::completion\_future 생성자](../Topic/completion_future::completion_future%20Constructor.md)|`completion_future` 클래스의 새 인스턴스를 초기화합니다.|  
|[completion\_future::~completion\_future 소멸자](../Topic/completion_future::~completion_future%20Destructor.md)|`completion_future` 개체를 소멸시킵니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[completion\_future::get 메서드](../Topic/completion_future::get%20Method.md)|연관된 비동기 작업이 완료될 때까지 기다립니다.|  
|[completion\_future::then 메서드](../Topic/completion_future::then%20Method.md)|관련 비동기 작업이 실행을 완료할 때 실행할 `completion_future` 개체에 대해 콜백 함수 개체를 연결합니다.|  
|[completion\_future::to\_task 메서드](../Topic/completion_future::to_task%20Method.md)|연결된 비동기 작업에 해당하는 `task` 개체를 반환합니다.|  
|[completion\_future::valid 메서드](../Topic/completion_future::valid%20Method.md)|개체가 비동기 작업에 연결되어 있는지 여부를 나타내는 부울 값을 가져옵니다.|  
|[completion\_future::wait 메서드](../Topic/completion_future::wait%20Method.md)|연결된 비동기 작업이 완료될 때까지 차단합니다.|  
|[completion\_future::wait\_for 메서드](../Topic/completion_future::wait_for%20Method.md)|연결된 비동기 작업이 완료되거나 `_Rel_time`에서 지정된 시간이 경과될 때까지 차단합니다.|  
|[completion\_future::wait\_until 메서드](../Topic/completion_future::wait_until%20Method.md)|관련된 비동기 작업이 완료되거나 현재 시간이 `_Abs_time`에 지정된 값을 초과할 때까지 차단합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[completion\_future::operator std::shared\_future\<void\> 연산자](../Topic/completion_future::operator%20std::shared_future%3Cvoid%3E%20Operator.md)|`completion_future` 개체를 `std::shared_future` 개체로 암시적으로 변환합니다.|  
|[completion\_future::operator\= 연산자](../Topic/completion_future::operator=%20Operator.md)|지정된 `completion_future` 개체의 내용을 여기로 복사합니다.|  
  
## 상속 계층  
 `completion_future`  
  
## 요구 사항  
 **헤더:** amprt.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [Concurrency 네임스페이스\(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)