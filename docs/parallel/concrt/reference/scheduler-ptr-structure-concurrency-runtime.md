---
title: "scheduler_ptr 구조체(동시성 런타임) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "pplinterface/concurrency::scheduler_ptr"
dev_langs: 
  - "C++"
ms.assetid: e88c84af-c306-476d-aef1-f42a0fa0a80f
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# scheduler_ptr 구조체(동시성 런타임)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

스케줄러에 대한 포인터를 나타냅니다.  이 클래스는 shared\_ptr을 사용하는 공유 수명 또는 원시 포인터를 사용하는 일반 참조의 사양을 허용하기 위해 존재합니다.  
  
## 구문  
  
```  
struct scheduler_ptr;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[scheduler\_ptr::scheduler\_ptr 생성자\(동시성 런타임\)](../Topic/scheduler_ptr::scheduler_ptr%20Constructor%20\(Concurrency%20Runtime\).md)|오버로드됨.  shared\_ptr에서 스케줄러에 대한 스케줄러 포인터를 만듭니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[scheduler\_ptr::get 메서드\(동시성 런타임\)](../Topic/scheduler_ptr::get%20Method%20\(Concurrency%20Runtime\).md)|스케줄러에 대한 원시 포인터를 반환합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[scheduler\_ptr::operator bool 연산자\(동시성 런타임\)](../Topic/scheduler_ptr::operator%20bool%20Operator%20\(Concurrency%20Runtime\).md)|스케줄러 포인터가 null이 아닌지 여부를 테스트합니다.|  
|[scheduler\_ptr::operator\-\> 연산자\(동시성 런타임\)](../Topic/scheduler_ptr::operator-%3E%20Operator%20\(Concurrency%20Runtime\).md)|포인터처럼 작동합니다.|  
  
## 상속 계층  
 `scheduler_ptr`  
  
## 요구 사항  
 **헤더:** pplinterface.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)