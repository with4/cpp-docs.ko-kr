---
title: "&lt;utility&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<utility>"
  - "utility/std::<utility>"
  - "std.<utility>"
  - "std::<utility>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "utility 헤더"
ms.assetid: c4491103-5da9-47a1-9c2b-ed8bc64b0599
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# &lt;utility&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

두 개체를 하나인 것처럼 처리해야 할 때 유용한 개체 쌍을 생성 및 관리하는 데 도움이 되는 STL\(표준 템플릿 라이브러리\) 형식, 함수 및 연산자를 정의합니다.  
  
## 구문  
  
```  
  
#include <utility>  
  
```  
  
## 설명  
 쌍은 표준 C\+\+ 라이브러리에서 널리 사용됩니다.  다양한 함수에 대한 인수 및 반환 값으로 및 [map 클래스](../standard-library/map-class.md)와 [multimap 클래스](../standard-library/multimap-class.md) 같은 컨테이너에 대한 요소 형식으로 필요합니다.  \<utility\> 헤더는 키\/값 쌍 형식 요소 관리를 지원하기 위해 자동으로 \<map\>에 포함됩니다.  
  
### 클래스  
  
|||  
|-|-|  
|[tuple\_element](../standard-library/tuple-element-class-utility.md)|`pair` 요소의 형식을 래핑하는 클래스입니다.|  
|[tuple\_size](../standard-library/tuple-size-class-utility.md)|`pair` 요소 수를 래핑하는 클래스입니다.|  
  
### Functions  
  
|||  
|-|-|  
|[forward](../Topic/forward.md)|완벽한 전달에 의해 가려지지 않도록 인수의 참조 형식\(`lvalue` 또는 `rvalue` 중 하나\)을 유지합니다.|  
|[Get](../Topic/get%20Function%20%3Cutility%3E.md)|`pair` 개체에서 요소를 가져오는 함수입니다.|  
|[make\_pair](../Topic/make_pair.md)|`pair` 형식의 개체를 생성하는 데 사용되는 템플릿 도우미 함수입니다. 여기서 구성 요소 형식은 매개 변수로 전달된 데이터 형식을 기반으로 합니다.|  
|[이동](../Topic/move.md)|전달된 인수를 `rvalue` 참조로 반환합니다.|  
|[스왑](../Topic/swap%20\(%3Cutility%3E\).md)|두 `pair` 개체의 요소를 교환합니다.|  
  
### 운영자  
  
|||  
|-|-|  
|[operator\!\=](../Topic/operator!=%20\(%3Cutility%3E\).md)|연산자의 좌변에 있는 pair 개체가 우변에 있는 pair 개체와 같지 않은지 테스트합니다.|  
|[연산자\=\=](../Topic/operator==%20\(%3Cutility%3E\).md)|연산자의 좌변에 있는 pair 개체가 우변에 있는 pair 개체와 같은지 테스트합니다.|  
|[operator \<](../Topic/operator%3C%20\(%3Cutility%3E\).md)|연산자의 좌변에 있는 pair 개체가 우변에 있는 pair 개체보다 작은지 테스트합니다.|  
|[operator \<\=](../Topic/operator%3C=%20\(%3Cutility%3E\).md)|연산자의 좌변에 있는 pair 개체가 우변에 있는 pair 개체보다 작은지 테스트합니다.|  
|[operator \>](../Topic/operator%3E%20\(%3Cutility%3E\).md)|연산자의 좌변에 있는 pair 개체가 우변에 있는 pair 개체보다 큰지 테스트합니다.|  
|[operator \>\=](../Topic/operator%3E=%20\(%3Cutility%3E\).md)|연산자의 좌변에 있는 pair 개체가 우변에 있는 pair 개체보다 크거나 같은지 테스트합니다.|  
  
### 구조체  
  
|||  
|-|-|  
|[ID](../standard-library/identity-structure.md)||  
|[pair](../standard-library/pair-structure.md)|두 개체를 단일 개체로 처리하는 기능을 제공하는 형식입니다.|  
  
## 참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)