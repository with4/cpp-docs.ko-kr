---
title: "condition_variable_any 클래스 | Microsoft Docs"
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
  - "condition_variable/std::condition_variable_any"
dev_langs: 
  - "C++"
ms.assetid: d8afe5db-1561-4ec2-8e85-21ea03ee4321
caps.latest.revision: 15
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# condition_variable_any 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

모든 `mutex` 형식을 사용하는 이벤트를 기다리는 `condition_variable_any` 클래스를 사용하세요.  
  
## 구문  
  
```  
class condition_variable_any;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[condition\_variable\_any::condition\_variable\_any 생성자](../Topic/condition_variable_any::condition_variable_any%20Constructor.md)|`condition_variable_any` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[condition\_variable\_any::notify\_all 메서드](../Topic/condition_variable_any::notify_all%20Method.md)|이 `condition_variable_any` 개체를 기다리는 모든 스레드를 차단해제합니다.|  
|[condition\_variable\_any::notify\_one 메서드](../Topic/condition_variable_any::notify_one%20Method.md)|이 `condition_variable_any` 개체를 기다리는 스레드 중 하나를 차단해제 합니다.|  
|[condition\_variable\_any::wait 메서드](../Topic/condition_variable_any::wait%20Method.md)|스레드를 차단합니다.|  
|[condition\_variable\_any::wait\_for 메서드](../Topic/condition_variable_any::wait_for%20Method.md)|스레드를 차단하고 스레드가 차단되는 시간 간격을 설정합니다.|  
|[condition\_variable\_any::wait\_until 메서드](../Topic/condition_variable_any::wait_until%20Method.md)|스레드를 차단 하고 스레드가 차단해제되는 시간의 최대 포인트를 설정합니다.|  
  
## 요구 사항  
 **Header:** condition\_variable  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [\<condition\_variable\>](../standard-library/condition-variable.md)