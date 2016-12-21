---
title: "independent_bits_engine 클래스 | Microsoft Docs"
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
  - "std.tr1.independent_bits_engine"
  - "std::tr1::independent_bits_engine"
  - "tr1::independent_bits_engine"
  - "tr1.independent_bits_engine"
  - "independent_bits_engine"
  - "random/std::tr1::independent_bits_engine"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "independent_bits_engine 클래스"
ms.assetid: 889e9a82-f457-49a7-9d2e-26e0fc3cd907
caps.latest.revision: 17
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# independent_bits_engine 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

기본 엔진에서 반환한 값의 비트를 다시 압축하여 지정된 수의 비트를 사용하여 숫자의 임의 시퀀스를 생성합니다.  
  
## 구문  
  
```  
template<class Engine, size_t W, class UIntType> class independent_bits_engine;  
```  
  
#### 매개 변수  
 `Engine`  
 기본 엔진 유형입니다.  
  
 `W`  
 **단어 크기**입니다.  생성된 각 수의 크기입니다\(비트\).  **사전 조건**: `0 < W ≤ numeric_limits<UIntType>::digits`  
  
 `UIntType`  
 부호가 없는 정수 결과 형식입니다.  가능한 형식은 [\<random\>](../standard-library/random.md)을 참조하세요.  
  
## 멤버  
  
||||  
|-|-|-|  
|`independent_bits_engine::independent_bits_engine`|`independent_bits_engine::base`|`independent_bits_engine::discard`|  
|`independent_bits_engine::operator()`|`independent_bits_engine::base_type`|`independent_bits_engine::seed`|  
  
 엔진 멤버에 대한 자세한 내용은 [\<random\>](../standard-library/random.md)을 참조하세요.  
  
## 설명  
 이 템플릿 클래스는 기본 엔진에서 반환하는 값의 비트를 다시 압축하여 `W`비트 값을 생성하는 *엔진 어댑터*에 대해 설명합니다.  
  
## 요구 사항  
 **헤더:** \<random\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<random\>](../standard-library/random.md)