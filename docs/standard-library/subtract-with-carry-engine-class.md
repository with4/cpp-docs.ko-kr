---
title: "subtract_with_carry_engine 클래스 | Microsoft Docs"
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
  - "tr1.subtract_with_carry_engine"
  - "std::tr1::subtract_with_carry_engine"
  - "random/std::tr1::subtract_with_carry_engine"
  - "subtract_with_carry_engine"
  - "tr1::subtract_with_carry_engine"
  - "std.tr1.subtract_with_carry_engine"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "subtract_with_carry_engine 클래스"
ms.assetid: 94a055f2-a620-4a22-ac34-c156924bab31
caps.latest.revision: 20
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# subtract_with_carry_engine 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

subtract\-with\-carry\(지연된 피보나치\) 알고리즘을 사용하여 임의 시퀀스를 생성합니다.  
  
## 구문  
  
```  
template<class UIntType, size_t W, size_t S, size_t R>  
class subtract_with_carry_engine;  
```  
  
#### 매개 변수  
 `UIntType`  
 부호가 없는 정수 결과 형식입니다. 가능한 형식에 대 한 참조 [\<random\>](../standard-library/random.md)합니다.  
  
 `W`  
 **단어 크기**입니다. 상태 시퀀스의 각 단어 크기입니다\(비트\).**사전 조건**: `0 < W ≤ numeric_limits<UIntType>::digits`  
  
 `S`  
 **짧은 지연**입니다. 정수 값의 개수입니다.**사전 조건**: `0 < S < R`  
  
 `R`  
 **긴 지연**입니다. 되풀이가 연속으로 발생했는지 확인합니다.  
  
## 멤버  
  
||||  
|-|-|-|  
|`subtract_with_carry_engine::subtract_with_carry_engine`|`subtract_with_carry_engine::min`|`subtract_with_carry_engine::discard`|  
|`subtract_with_carry_engine::operator()`|`subtract_with_carry_engine::max`|`subtract_with_carry_engine::seed`|  
|`default_seed`는 `19780503u`로 정의된 멤버 상수로, `subtract_with_carry_engine::seed` 및 단일 값 생성자의 기본 매개 변수 값으로 사용됩니다.|||  
  
 엔진 멤버에 대 한 자세한 내용은 참조 [\<random\>](../standard-library/random.md)합니다.  
  
## 설명  
 `substract_with_carry_engine` 템플릿 클래스는 [linear\_congruential\_engine](../standard-library/linear-congruential-engine-class.md)보다 향상되었습니다. 이러한 엔진 둘 다 [mersenne\_twister\_engine](../standard-library/mersenne-twister-engine-class.md)만큼 빠르거나 품질 결과가 뛰어나지 않습니다.  
  
 이 엔진은 되풀이 관계\(*기간*\)를 사용하여 사용자가 지정한 부호가 없는 정수 형식의 값을 생성합니다. `x(i) = (x(i - R) - x(i - S) - cy(i - 1)) mod M` 여기서 `cy(i)`의 값은 `1`입니다. `x(i - S) - x(i - R) - cy(i - 1) < 0`인 경우 이 값이 1입니다. 그렇지 않으면 `0`입니다. `M`의 값은 `2`<sup>W</sup>입니다. 엔진의 상태는 전달 표시기 \+ `R` 값입니다. 이러한 값은 마지막 `R` 값으로 구성됩니다. `operator()`가 `R`번 호출된 경우 그렇습니다. 그렇지 않으면 반환된 `N` 값과 시드의 마지막 `R - N` 값으로 구성됩니다.  
  
 템플릿 인수 `UIntType`은 최대 `M - 1`까지 값을 보유할 수 있도록 충분히 커야 합니다.  
  
 이 엔진 생성기에서 직접 생성할 수 있지만 이러한 미리 정의 된 typedef 중 하나도 사용할 수 있습니다.  
  
 `ranlux24_base`:에 대 한 기준으로 사용 합니다. `ranlux24`합니다.  
`typedef subtract_with_carry_engine<unsigned int, 24, 10, 24> ranlux24_base;`  
  
 `ranlux48_base`:에 대 한 기준으로 사용 합니다. `ranlux48`합니다.  
`typedef subtract_with_carry_engine<unsigned long long, 48, 5, 12> ranlux48_base;`  
  
 Subract와 엔진 알고리즘에 대 한 자세한 내용은 Wikipedia 문서를 참조 하십시오. [지연 된 피보나치 생성기](http://go.microsoft.com/fwlink/?LinkId=402445)합니다.  
  
## 요구 사항  
 **헤더:** \<random\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<random\>](../standard-library/random.md)