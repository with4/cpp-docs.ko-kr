---
title: "task_continuation_context 클래스 | Microsoft Docs"
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
  - "ppltasks/concurrency::task_continuation_context"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "task_continuation_context 클래스"
ms.assetid: 1fb5a76a-3682-45c2-a615-8b6b527741f0
caps.latest.revision: 15
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# task_continuation_context 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`task_continuation_context` 클래스를 사용하면 연속 작업을 실행할 위치를 지정할 수 있습니다.  Windows 스토어 응용 프로그램에서 이 클래스를 사용하는 경우에만 유용합니다.  Windows 스토어 응용 프로그램이 아닌 경우 작업 연속의 실행 컨텍스트가 실행 시간에 의해 결정되며 구성할 수 없습니다.  
  
## 구문  
  
```  
class task_continuation_context : public details::_ContextCallback;  
```  
  
## 멤버  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[task\_continuation\_context::use\_arbitrary 메서드](../Topic/task_continuation_context::use_arbitrary%20Method.md)|런타임이 실행 컨텍스트를 연속으로 선택할 수 있도록 해주는 작업 연속 컨텍스트를 만듭니다.|  
|[task\_continuation\_context::use\_current 메서드](../Topic/task_continuation_context::use_current%20Method.md)|현재 실행 컨텍스트를 나타내는 작업 연속 컨텍스트 개체를 반환합니다.|  
|[task\_continuation\_context::use\_default 메서드](../Topic/task_continuation_context::use_default%20Method.md)|기본 작업 연속 컨텍스트를 만듭니다.|  
  
## 상속 계층  
 `_ContextCallback`  
  
 `task_continuation_context`  
  
## 요구 사항  
 **헤더:** ppltasks.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [task Class](http://msdn.microsoft.com/ko-kr/5389e8a5-5038-40b6-844a-55e9b58ad35f)