---
title: "gslice 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::gslice"
  - "std.gslice"
  - "gslice"
  - "valarray/std::gslice"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "gslice 클래스"
ms.assetid: f47cffd0-ea59-4b13-848b-7a5ce1d7e2a3
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# gslice 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

valarray의 다차원 하위 집합을 정의하는 데 사용되는 valarray에 대한 유틸리티 클래스입니다.  valarray가 배열의 모든 요소를 포함하는 다차원 행렬로 간주되는 경우 조각은 다차원 배열에서 벡터를 추출합니다.  
  
## 설명  
 클래스는 [gslice\_array](../standard-library/gslice-array-class.md) 형식의 개체 특징을 결정하는 매개 변수를 저장합니다.  gslice 클래스의 개체가 [valarray](../Topic/valarray::operator.md)**\<Type\>** 클래스의 개체에 대한 인수로 표시되는 경우 valarray의 하위 집합이 간접적으로 생성됩니다.  부모 valarray에서 선택되는 하위 집합을 지정하는 저장된 값은 다음과 같습니다.  
  
-   시작 인덱스  
  
-   **valarray\<size\_t\>** 클래스의 길이 벡터  
  
-   **valarray\<size\_t\>** 클래스의 진행 속도 벡터  
  
 두 벡터는 길이가 같아야 합니다.  
  
 gslice에서 정의된 집합이 상수 valarray의 하위 집합인 경우 gslice은 새 valarray입니다.  gslice에서 정의된 집합이 비상수 valarray의 하위 집합인 경우 gslice에 원래 valarray에 대한 참조 의미 체계가 있습니다.  비상수 valarray에 대한 평가 메커니즘은 시간과 메모리를 절약합니다.  
  
 gslice에서 정의된 소스 및 대상 하위 집합이 고유하고 모든 인덱스가 유효한 경우에만 valarray에 대한 작업이 보장됩니다.  
  
### 생성자  
  
|||  
|-|-|  
|[gslice](../Topic/gslice::gslice.md)|모두 지정된 요소에서 시작하는 `valarray`의 여러 조각으로 구성된 `valarray`의 하위 집합을 정의합니다.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[size](../Topic/gslice::size.md)|`valarray`의 일반 조각 요소 수를 지정하는 배열 값을 찾습니다.|  
|[시작](../Topic/gslice::start.md)|`valarray`의 일반 조각 시작 인덱스를 찾습니다.|  
|[stride](../Topic/gslice::stride.md)|`valarray`의 일반 조각 요소 간의 거리를 찾습니다.|  
  
## 요구 사항  
 **Header:** \<valarray\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)