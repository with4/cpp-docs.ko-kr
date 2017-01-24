---
title: "condition_variable 클래스 | Microsoft Docs"
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
  - "condition_variable/std::condition_variable"
dev_langs: 
  - "C++"
ms.assetid: 80b1295c-b73d-4d46-b664-6e183f2eec1b
caps.latest.revision: 16
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# condition_variable 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

형식 `unique_lock<mutex>` 의 `mutex` 를 가지고 있는 경우 이벤트를 기다리기 위해 `condition_variable` 클래스를 사용합니다.  이 형식의 개체의 경우 형식 [condition\_variable\_any\<unique\_lock\<mutex\>\>](../standard-library/condition-variable-any-class.md)의 개체보다 더 나은 성능을 가질 수 있습니다.  
  
## 구문  
  
```  
class condition_variable;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[condition\_variable::condition\_variable 생성자](../Topic/condition_variable::condition_variable%20Constructor.md)|`condition_variable` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[condition\_variable::native\_handle 메서드](../Topic/condition_variable::native_handle%20Method.md)|Condition\_variable 핸들을 나타내는 구현이 지정된 형식을 반환 합니다.|  
|[condition\_variable::notify\_all 메서드](../Topic/condition_variable::notify_all%20Method.md)|`condition_variable` 개체를 기다리는 모든 스레드를 차단해제합니다.|  
|[condition\_variable::notify\_one 메서드](../Topic/condition_variable::notify_one%20Method.md)|`condition_variable` 개체를 기다리는 스레드 중 하나를 차단해제 합니다.|  
|[condition\_variable::wait 메서드](../Topic/condition_variable::wait%20Method.md)|스레드를 차단합니다.|  
|[condition\_variable::wait\_for 메서드](../Topic/condition_variable::wait_for%20Method.md)|스레드를 차단하고 스레드가 차단되는 시간 간격을 설정합니다.|  
|[condition\_variable::wait\_until 메서드](../Topic/condition_variable::wait_until%20Method.md)|스레드를 차단 하고 스레드가 차단해제되는 시간의 최대 포인트를 설정합니다.|  
  
## 요구 사항  
 **Header:** condition\_variable  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [\<condition\_variable\>](../standard-library/condition-variable.md)