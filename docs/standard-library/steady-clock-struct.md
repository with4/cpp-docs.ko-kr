---
title: "steady_clock 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "chrono/std::chrono::steady_clock"
dev_langs: 
  - "C++"
ms.assetid: 970d12ec-fc80-4391-a2f7-b57b2aec668d
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# steady_clock 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`steady` 클록을 나타냅니다.  
  
## 구문  
  
```  
struct steady_clock;  
```  
  
## 설명  
 Windows에서 steady\_clock은 QueryPerformanceCounter 함수를 래핑합니다.  
  
 `now()`에 대한 첫 번째 호출에서 반환되는 값이 항상 `now()`에 대한 순차적 호출에서 반환되는 값보다 작거나 같을 경우 클록은 *단조*입니다.  
  
 클록이 *단조*이고 클록 틱 간 시간이 지속적이면 클록은 *지속*입니다.  
  
 High\_resolution\_clock은 steady\_clock에 대한 typedef입니다.  
  
## 공용 함수  
  
|함수|설명|  
|--------|--------|  
|now|현재 시간을 time\_point 값으로 반환합니다.|  
  
## 공용 상수  
  
|이름|설명|  
|--------|--------|  
|`system_clock::is_steady`|`true`입니다.  `steady_clock`은 *지속*입니다.|  
  
## 요구 사항  
 **헤더:** chrono  
  
 **네임스페이스:** std::chrono  
  
## 참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono\>](../standard-library/chrono.md)   
 [system\_clock 구조체](../standard-library/system-clock-structure.md)