---
title: "system_clock 구조체 | Microsoft Docs"
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
  - "chrono/std::chrono::system_clock"
dev_langs: 
  - "C++"
ms.assetid: a97bd46e-267a-4836-9f7d-af1f664e99ae
caps.latest.revision: 14
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# system_clock 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

시스템의 실시간 시계를 기준으로 하는 *시간 형식*을 나타냅니다.  
  
## 구문  
  
```  
struct system_clock;  
```  
  
## 설명  
 *시간 형식*은 현재 시간을 UTC로 가져오는 데 사용됩니다.  이 형식은 [duration](../standard-library/duration-class.md) 및 클래스 템플릿 [time\_point](../standard-library/time-point-class.md)의 인스턴스화를 구현하고 시간을 반환하는 정적 멤버 함수 `now()`를 정의합니다.  
  
 `now()`에 대한 첫 번째 호출에서 반환되는 값이 항상 `now()`에 대한 순차적 호출에서 반환되는 값보다 작거나 같을 경우 클록은 *단조*입니다.  
  
 클록이 *단조*이고 클록 틱 간 시간이 지속적이면 클록은 *지속*입니다.  
  
 이 구현에서 `system_clock`은 `high_resolution_clock`와 의미가 같습니다.  
  
## 멤버  
  
### 공용 Typedefs  
  
|이름|설명|  
|--------|--------|  
|`system_clock::duration`|`duration<rep, period>`의 동의어입니다.|  
|`system_clock::period`|`duration`의 포함된 인스턴스화에서 틱 기간을 나타내는 데 사용되는 형식의 동의어입니다.|  
|`system_clock::rep`|`duration`의 포함된 인스턴스화에서 클록 틱 수를 나타내는 데 사용되는 형식의 동의어입니다.|  
|`system_clock::time_point`|`time_point<Clock, duration>`의 동의어입니다. 여기서, `Clock`은 클록 형식 자체의 동의어이거나 같은 Epoch에 기반을 두고 같은 중첩된 `duration` 형식을 포함하는 또 다른 클록 형식의 동의어입니다.|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[system\_clock::from\_time\_t 메서드](../Topic/system_clock::from_time_t%20Method.md)|정적.  지정된 시간과 가장 가까운 근사치로 계산된 `time_point`를 반환합니다.|  
|[system\_clock::now 메서드](../Topic/system_clock::now%20Method.md)|정적.  현재 시간을 반환합니다.|  
|[system\_clock::to\_time\_t 메서드](../Topic/system_clock::to_time_t%20Method.md)|정적.  지정된 `time_point`와 가장 가까운 근사치로 계산된 `time_t` 개체를 반환합니다.|  
  
### 공용 상수  
  
|이름|설명|  
|--------|--------|  
|[system\_clock::is\_monotonic 상수](../Topic/system_clock::is_monotonic%20Constant.md)|클록 형식이 단조인지를 지정합니다.|  
|[system\_clock::is\_steady 상수](../Topic/system_clock::is_steady%20Constant.md)|클록 형식이 지속인지를 지정합니다.|  
  
## 요구 사항  
 **헤더:** chrono  
  
 **네임스페이스:** std::chrono  
  
## 참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono\>](../standard-library/chrono.md)   
 [steady\_clock 구조체](../standard-library/steady-clock-struct.md)