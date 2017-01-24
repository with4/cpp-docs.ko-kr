---
title: "promise 클래스 | Microsoft Docs"
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
  - "future/std::promise"
dev_langs: 
  - "C++"
ms.assetid: 2931558c-d94a-4ba1-ac4f-20bf7b6e23f9
caps.latest.revision: 15
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# promise 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 *비동기 공급자* 를 설명합니다.  
  
## 구문  
  
```  
template<class Ty>  
class promise;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[promise::promise 생성자](../Topic/promise::promise%20Constructor.md)|`promise` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[promise::get\_future 메서드](../Topic/promise::get_future%20Method.md)|반환된 [이후](../standard-library/future-class.md) 이 완성도와 관련됩니다.|  
|[promise::set\_exception 메서드](../Topic/promise::set_exception%20Method.md)|예외를 나타내기 위해 이 약속의 결과 자동 설정 합니다.|  
|[promise::set\_exception\_at\_thread\_exit 메서드](../Topic/promise::set_exception_at_thread_exit%20Method.md)|예외를 나타내기 위해 결국 스레드 지역 개체 현재 스레드가 알림을 배달\(대개 스레드 종료\)에 결과를 자동적으로 설정합니다.|  
|[promise::set\_value 메서드](../Topic/promise::set_value%20Method.md)|원자적으로 값을 나타내려면이 약속의 결과 설정 합니다.|  
|[promise::set\_value\_at\_thread\_exit 메서드](../Topic/promise::set_value_at_thread_exit%20Method.md)|값를 나타내기 위해 결국 스레드 지역 개체 현재 스레드가 알림을 배달\(대개 스레드 종료\)에 결과를 자동적으로 설정합니다.|  
|[promise::swap 메서드](../Topic/promise::swap%20Method.md)|이 *연관 된 비동기 상태* 약속 지정된 개체를 사용하여 이 약속을 교환합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[promise::operator\= 연산자](../Topic/promise::operator=%20Operator.md)|이 약속 개체의 공유 상태가 할당 합니다.|  
  
## 상속 계층  
 `promise`  
  
## 요구 사항  
 **헤더:** future  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)