---
title: "numeric_limits 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::numeric_limits"
  - "std.numeric_limits"
  - "numeric_limits"
  - "limits/std::numeric_limits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "numeric_limits 클래스"
ms.assetid: 9e817177-0e91-48e6-b680-0531c4b26625
caps.latest.revision: 26
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 26
---
# numeric_limits 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 템플릿 클래스는 기본 제공 숫자 형식의 산술 속성을 설명합니다.  
  
## 구문  
  
```  
template<classType> class numeric_limits  
```  
  
#### 매개 변수  
 `Type`  
 속성이 테스트, 쿼리 또는 설정되는 기본 요소 데이터 형식입니다.  
  
## 설명  
 헤더는 `wchar_t`, `bool`, `char`, `signed char`, `unsigned char`, `short`, `unsigned short`, `int`, `unsigned int`, `long`, `unsigned long`, `float`, `double`, `long double`**,** `long long`, `unsigned long long`, `char16_t` 및 `char32_t` 형식에 대한 명시적 특수화를 정의합니다. 이러한 명시적 특수화의 경우 [numeric\_limits::is\_specialized](../Topic/numeric_limits::is_specialized.md) 멤버가 `true`이며 모든 관련 멤버에 의미 있는 값이 있습니다. 프로그램에서 추가 명시적 특수화를 제공할 수 있습니다. 클래스의 대다수 멤버 함수는 `float`의 가능한 구현을 설명하거나 테스트합니다.  
  
 임의 특수화의 경우 멤버에 의미 있는 값이 없습니다. 의미 있는 값이 없는 멤버 개체는 0\(또는 `false`\)를 저장하고 의미 있는 값을 반환하지 않는 멤버 함수는 `Type(0)`을 반환합니다.  
  
### 정적 함수 및 상수  
  
|||  
|-|-|  
|[denorm\_min](../Topic/numeric_limits::denorm_min.md)|0이 아닌 가장 작은 비정규화된 값을 반환합니다.|  
|[digits](../Topic/numeric_limits::digits.md)|정밀도의 손실 없이 형식이 나타낼 수 있는 기수 자릿수를 반환합니다.|  
|[digits10](../Topic/numeric_limits::digits10.md)|정밀도의 손실 없이 형식이 나타낼 수 있는 10진수 자릿수를 반환합니다.|  
|[epsilon](../Topic/numeric_limits::epsilon.md)|1과 데이터 형식이 나타낼 수 있는 1보다 큰 가장 작은 값 사이의 차이를 반환합니다.|  
|[has\_denorm](../Topic/numeric_limits::has_denorm.md)|형식이 비정규화된 값을 허용하는지 테스트합니다.|  
|[has\_denorm\_loss](../Topic/numeric_limits::has_denorm_loss.md)|정밀도 손실이 부정확한 결과가 아니라 비정규화 손실로 검색되는지 테스트합니다.|  
|[has\_infinity](../Topic/numeric_limits::has_infinity.md)|형식에 양의 무한대 표현이 있는지 테스트합니다.|  
|[has\_quiet\_NaN](../Topic/numeric_limits::has_quiet_NaN.md)|형식에 신호를 보내지 않는 자동 NAN\(숫자가 아님\) 표현이 있는지 테스트합니다.|  
|[has\_signaling\_NaN](../Topic/numeric_limits::has_signaling_NaN.md)|형식에 신호를 보내는 NAN\(숫자가 아님\) 표현이 있는지 테스트합니다.|  
|[infinity](../Topic/numeric_limits::infinity.md)|형식에 대한 양의 무한대 표현\(사용 가능한 경우\)입니다.|  
|[is\_bounded](../Topic/numeric_limits::is_bounded.md)|형식이 나타낼 수 있는 값 집합이 유한한지 테스트합니다.|  
|[is\_exact](../Topic/numeric_limits::is_exact.md)|형식에서 수행되는 계산에 반올림 오류가 없는지 테스트합니다.|  
|[is\_iec559](../Topic/numeric_limits::is_iec559.md)|형식이 IEC 559 표준을 준수하는지 테스트합니다.|  
|[is\_integer](../Topic/numeric_limits::is_integer.md)|형식이 정수 표현인지 테스트합니다.|  
|[is\_modulo](../Topic/numeric_limits::is_modulo.md)|형식에 모듈로 표현이 있는지 테스트합니다.|  
|[is\_signed](../Topic/numeric_limits::is_signed.md)|형식에 부호 있는 표현이 있는지 테스트합니다.|  
|[is\_specialized](../Topic/numeric_limits::is_specialized.md)|형식에 템플릿 클래스 `numeric_limits`에 정의된 명시적 특수화가 있는지 테스트합니다.|  
|[lowest](../Topic/numeric_limits::lowest.md)|최대한의 음의 무한대 값을 반환합니다.|  
|[max](../Topic/numeric_limits::max.md)|형식에 대한 유한 최대값을 반환합니다.|  
|[max\_digits10](../Topic/numeric_limits::max_digits10.md)|형식의 두 고유 값에 고유 10진수 표현이 있는지 확인하는 데 필요한 10진수 자릿수를 반환합니다.|  
|[max\_exponent](../Topic/numeric_limits::max_exponent.md)|밑수 기수에 대한 해당 거듭제곱을 계산할 때 부동 소수점 형식이 유한 값으로 나타낼 수 있는 최대 양의 정수 지수를 반환합니다.|  
|[max\_exponent10](../Topic/numeric_limits::max_exponent10.md)|밑수 10에 대한 해당 거듭제곱을 계산할 때 부동 소수점 형식이 유한 값으로 나타낼 수 있는 최대 양의 정수 지수를 반환합니다.|  
|[분](../Topic/numeric_limits::min.md)|형식에 대한 정규화된 최소값을 반환합니다.|  
|[min\_exponent](../Topic/numeric_limits::min_exponent.md)|밑수 기수에 대한 해당 거듭제곱을 계산할 때 부동 소수점 형식이 유한 값으로 나타낼 수 있는 최대 음의 정수 지수를 반환합니다.|  
|[min\_exponent10](../Topic/numeric_limits::min_exponent10.md)|밑수 10에 대한 해당 거듭제곱을 계산할 때 부동 소수점 형식이 유한 값으로 나타낼 수 있는 최대 음의 정수 지수를 반환합니다.|  
|[quiet\_NaN](../Topic/numeric_limits::quiet_NaN.md)|형식에 대한 자동 NAN\(숫자가 아님\) 표현을 반환합니다.|  
|[radix](../Topic/numeric_limits::radix.md)|형식 표현에 사용되는 정수 밑수\(기수라고도 함\)를 반환합니다.|  
|[round\_error](../Topic/numeric_limits::round_error.md)|형식에 대한 최대 반올림 오차를 반환합니다.|  
|[round\_style](../Topic/numeric_limits::round_style.md)|구현에서 부동 소수점 값을 정수 값으로 반올림하기 위해 선택할 수 있는 다양한 메서드를 설명하는 값을 반환합니다.|  
|[signaling\_NaN](../Topic/numeric_limits::signaling_NaN.md)|형식에 대한 신호를 보내는 NAN\(숫자가 아님\) 표현을 반환합니다.|  
|[tinyness\_before](../Topic/numeric_limits::tinyness_before.md)|값이 너무 작아서 반올림하기 전에 정규화된 값으로 나타낼 수 없음을 형식이 확인할 수 있는지 테스트합니다.|  
|[traps](../Topic/numeric_limits::traps.md)|산술 예외를 보고하는 트래핑이 형식에 대해 구현되었는지 테스트합니다.|  
  
## 요구 사항  
 **헤더:** \<limits\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)