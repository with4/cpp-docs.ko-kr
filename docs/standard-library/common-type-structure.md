---
title: "common_type 구조체 | Microsoft Docs"
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
  - "chrono/std::common_type"
dev_langs: 
  - "C++"
ms.assetid: 2b42722c-c3dc-4d62-8613-0271e52b6f00
caps.latest.revision: 13
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# common_type 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 [duration](../standard-library/duration-class.md) 와 [time\_point](../standard-library/time-point-class.md) 의 인스턴스화의 [common\_type](../standard-library/common-type-class.md) 템플릿 클레스의 특수화를 설명합니다.  
  
## 구문  
  
```  
template<class Rep1, class Period1,  
   class Rep2, class Period2>  
struct common_type  
<chrono::duration<Rep1, Period1>,   
chrono::duration<Rep2, Period2>>;  
  
template<class Clock,  
   class Duration1, class Duration2>  
struct common_type  
<chrono::time_point<Clock, Duration1>,  
chrono::time_point<Clock, Duration2>>;  
```  
  
## 요구 사항  
 **Header:** chrono  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono\>](../standard-library/chrono.md)