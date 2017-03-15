---
title: "time_point 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "chrono/std::chrono::time_point"
dev_langs: 
  - "C++"
ms.assetid: 18be1e52-57b9-489a-8a9b-f58894f0aaad
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# time_point 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 `time_point` 시간에서을 나타내는 형식에 설명 합니다.  템플릿 인수 `Clock` 로 나타나진 기원 이후로 경과한 시간 저장하는 형식 [기간](../standard-library/duration-class.md) 의 개체를 보유합니다.  
  
## 구문  
  
```  
template<  
   class Clock,  
   class Duration = typename Clock::duration  
>  
class time_point;  
```  
  
## 멤버  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|`time_point::clock`|템플릿 매개 변수 `Clock`에 대한 동의어.|  
|`time_point::duration`|템플릿 매개 변수 `Duration`에 대한 동의어.|  
|`time_point::period`|중첩 된 형식 이름 `duration::period`에 대한 동의어.|  
|`time_point::rep`|중첩 된 형식 이름 `duration::rep`에 대한 동의어.|  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[time\_point::time\_point 생성자](../Topic/time_point::time_point%20Constructor.md)|`time_point` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[time\_point::max 메서드](../Topic/time_point::max%20Method.md)|이 `time_point::ref`에 대한 상한값을 지정.|  
|[time\_point::min 메서드](../Topic/time_point::min%20Method.md)|이 `time_point::ref`에 대한 하한값을 지정.|  
|[time\_point::time\_since\_epoch 메서드](../Topic/time_point::time_since_epoch%20Method.md)|저장한 `duration` 값을 반환합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[time\_point::operator\+\= 연산자](../Topic/time_point::operator+=%20Operator.md)|저장된 기간에 지정된 값을 추가합니다.|  
|[time\_point::operator\-\= 연산자](../Topic/time_point::operator-=%20Operator.md)|저장하는 동안 지정된 값을 뺍니다.|  
  
## 요구 사항  
 **Header:** chrono  
  
 **네임 스페이스:** std::chrono  
  
## 참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono\>](../standard-library/chrono.md)