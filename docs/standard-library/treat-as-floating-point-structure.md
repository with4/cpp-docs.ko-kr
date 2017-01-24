---
title: "treat_as_floating_point 구조체 | Microsoft Docs"
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
  - "chrono/std::chrono::treat_as_floating_point"
dev_langs: 
  - "C++"
ms.assetid: d0a2161c-bbb2-4924-8961-7568d5ad5434
caps.latest.revision: 13
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# treat_as_floating_point 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 `Rep` 이 부동 소수점 형식으로 처리할 수 있을지 여부를 지정하세요.  
  
## 구문  
  
```  
template<class Rep>  
struct treat_as_floating_point : is_floating_point<Rep>;  
```  
  
## 설명  
 `Rep` 는 [true\_type](../Topic/true_type%20Typedef.md) 으로 파생된 `treat_as_floating_point<Rep>` 으로 전문화 되었을 때, 부동 소수점 형식으로 다룰 수 있습니다.  사용자 정의 형식에 대한 템플릿 클래스를 특수화할 수 있습니다.  
  
## 요구 사항  
 **Header:** chrono  
  
 **네임 스페이스:** std::chrono  
  
## 참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono\>](../standard-library/chrono.md)