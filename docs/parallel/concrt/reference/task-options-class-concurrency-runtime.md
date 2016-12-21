---
title: "task_options 클래스(동시성 런타임) | Microsoft Docs"
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
  - "ppltasks/concurrency::task_options"
dev_langs: 
  - "C++"
ms.assetid: f93d146b-70f7-46ec-8c2f-c33b8bb0af69
caps.latest.revision: 7
caps.handback.revision: 1
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# task_options 클래스(동시성 런타임)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

작업을 만드는 데 허용된 옵션을 나타냅니다.  
  
## 구문  
  
```  
class task_options;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[task\_options::task\_options 생성자\(동시성 런타임\)](../Topic/task_options::task_options%20Constructor%20\(Concurrency%20Runtime\).md)|오버로드됨.  작업 만들기 옵션의 기본 목록|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[task\_options::get\_cancellation\_token 메서드\(동시성 런타임\)](../Topic/task_options::get_cancellation_token%20Method%20\(Concurrency%20Runtime\).md)|취소 토큰을 반환합니다.|  
|[task\_options::get\_continuation\_context 메서드\(동시성 런타임\)](../Topic/task_options::get_continuation_context%20Method%20\(Concurrency%20Runtime\).md)|연속 컨텍스트를 반환합니다.|  
|[task\_options::get\_scheduler 메서드\(동시성 런타임\)](../Topic/task_options::get_scheduler%20Method%20\(Concurrency%20Runtime\).md)|스케줄러 반환|  
|[task\_options::has\_cancellation\_token 메서드\(동시성 런타임\)](../Topic/task_options::has_cancellation_token%20Method%20\(Concurrency%20Runtime\).md)|사용자가 취소 토큰을 지정했는지 여부를 나타냅니다.|  
|[task\_options::has\_scheduler 메서드\(동시성 런타임\)](../Topic/task_options::has_scheduler%20Method%20\(Concurrency%20Runtime\).md)|사용자가 스케줄러 n을 지정했는지 여부를 나타냅니다.|  
|[task\_options::set\_cancellation\_token 메서드\(동시성 런타임\)](../Topic/task_options::set_cancellation_token%20Method%20\(Concurrency%20Runtime\).md)|옵션에서 지정된 토큰을 설정합니다.|  
|[task\_options::set\_continuation\_context 메서드\(동시성 런타임\)](../Topic/task_options::set_continuation_context%20Method%20\(Concurrency%20Runtime\).md)|옵션에서 지정된 연속 작업 컨텍스트를 설정합니다.|  
  
## 상속 계층  
 `task_options`  
  
## 요구 사항  
 **헤더:** ppltasks.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)