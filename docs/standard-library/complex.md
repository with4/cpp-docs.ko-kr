---
title: "&lt;complex&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<complex>"
  - "std.<complex>"
  - "std::<complex>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "complex 헤더"
ms.assetid: 5e728995-3059-496a-9ce9-61d1bfbe4f2b
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# &lt;complex&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

컨테이너 템플릿 클래스 컴플렉스 및 해당 지원 템플릿을 정의합니다.  
  
## 구문  
  
```  
  
#include <complex>  
  
```  
  
## 설명  
 복소수는 실수의 순서가 지정된 쌍입니다.  순수하게 기하학적 측면에서 복합 평면은 실제 2차원 평면입니다.  실제 평면과 구분되는 복합 평면의 특성은 추가 대수 구조가 있기 때문입니다.  이 대수 구조에는 두 가지 기본 작업이 있습니다.  
  
-   \(*a, b*\) \+ \(*c, d*\) \= \(*a \+ c, b \+ d\)*로 정의되는 더하기  
  
-   \(*a, b*\) \* \(*c, d*\) \= \(*ac \- bd, ad \+ bc*\)로 정의되는 곱하기  
  
 복합 더하기 및 복합 곱하기 연산이 있는 복소수 집합은 표준 대수 측면에서 필드입니다.  
  
-   더하기 및 곱하기 연산은 누적 및 연결되고, 실수 필드의 실제 더하기 및 곱하기와 마찬가지로 곱하기가 더하기에 배포됩니다.  
  
-   복소수\(*0, 0*\)는 덧셈 ID이고 \(*1, 0*\)은 곱셈 ID입니다.  
  
-   복소수\(*a, b*\)의 덧셈 역수는 \(*\-a, \-b*\)이고 \(*0, 0*\)을 제외한 이러한 모든 복소수의 곱셈 역수는 다음과 같습니다.  
  
     \(*a*\/\(*a*<sup>2</sup> \+ *b*<sup>2</sup>\), \-*b*\/\(*a*<sup>2</sup> \+ *b*<sup>2</sup>\)  
  
 복소수 *z \= \(a, b\)*를 *z \= a \+ bi* 형태\(여기서 *i*<sup>2</sup> *\=* \-1\)로 표시하면 복소수 집합 및 해당 구성 요소에 실수 집합의 대수 규칙을 적용할 수 있습니다.  예를 들면 다음과 같습니다.  
  
 \(1 \+ 2*i*\) \* \(2 \+ 3*i*\)    \= 1\*\(2 \+ 3*i*\) \+ 2*i*\*\(2 \+ 3*i*\) \= \(2 \+ 3*i*\) \+ \(4*i* \+ 6*i*<sup>2</sup>\)  
  
 \= \(2 –6\) \+ \(3 \+ 4\)*i* \= \-4 \+ 7*i*  
  
 복소수 시스템은 필드이지만 순서가 지정된 필드가 아닙니다.  필드 또는 실수와 해당 하위 집합과 달리 복소수에는 순서가 없으므로 순서가 지정된 필드인 실수와 달리 복소수에는 같지 않음을 적용할 수 없습니다.  
  
 복소수 *z*를 나타내는 일반적인 형태에는 다음 세 가지가 있습니다.  
  
-   데카르트: *z \= a \+ bi*  
  
-   극좌표형: *z \= r* \(cos *\+ i*sin\)  
  
-   지수: *z \= r \** exp\(\)  
  
 복소수의 이러한 표준 표현에 사용되는 용어는 다음과 같이 참조됩니다.  
  
-   데카르트 실수 구성 요소 또는 실수 부분 *a*  
  
-   데카르트 허수 구성 요소 또는 허수 부분 *b*  
  
-   복소수 Ρ의 모듈러스 또는 절대값  
  
-   인수 또는 위상각  
  
 달리 지정되지 않은 경우 여러 값을 반환할 수 있는 함수는 단일 값으로 유지하기 위해 \-pi보다 크고 \+pi보다 작거나 같은 인수에 대해 주 값을 반환해야 합니다.  모든 각도는 라디안으로 표현되어야 합니다. 이 경우 원에는 2pi 라디안\(360도\)이 있습니다.  
  
### 함수  
  
|||  
|-|-|  
|[abs](../Topic/abs.md)|복소수의 모듈러스를 계산합니다.|  
|[arg](../Topic/arg.md)|복소수에서 인수를 추출합니다.|  
|[conj](../Topic/conj.md)|복소수의 켤레 복소수를 반환합니다.|  
|[cos](../Topic/cos.md)|복소수의 코사인을 반환합니다.|  
|[cosh](../Topic/cosh.md)|복소수의 쌍곡 코사인을 반환합니다.|  
|[exp](../Topic/exp.md)|복소수의 지수 함수를 반환합니다.|  
|[imag](../Topic/imag.md)|복소수의 허수 구성 요소를 추출합니다.|  
|[log](../Topic/log.md)|복소수의 자연 로그를 반환합니다.|  
|[log10](../Topic/log10.md)|복소수의 상용 로그를 반환합니다.|  
|[norm](../Topic/norm.md)|복소수 기준을 추출합니다.|  
|[polar](../Topic/polar.md)|지정한 모듈러스 및 인수에 해당하는 복소수를 데카르트 형태로 반환합니다.|  
|[pow](../Topic/pow.md)|복소수인 밑수를 다른 복소수로 거듭제곱하여 얻은 복소수를 계산합니다.|  
|[실수](../Topic/real.md)|복소수의 실수 구성 요소를 추출합니다.|  
|[sin](../Topic/sin.md)|복소수의 사인을 반환합니다.|  
|[sinh](../Topic/sinh.md)|복소수의 쌍곡 사인을 반환합니다.|  
|[sqrt](../Topic/sqrt.md)|복소수의 제곱근을 반환합니다.|  
|[tan](../Topic/Functions%20tan.md)|복소수의 탄젠트를 반환합니다.|  
|[tanh](../Topic/tanh.md)|복소수의 쌍곡 탄젠트를 반환합니다.|  
  
### 연산자  
  
|||  
|-|-|  
|[operator\!\=](../Topic/operator!=%20\(%3Ccomplex%3E\).md)|하나 또는 둘 모두 실수 및 허수 부분에서 형식의 일부에 속할 수 있는 두 복소수를 같지 않은지 테스트합니다.|  
|[operator\*](../Topic/operator*%20\(%3Ccomplex%3E\).md)|하나 또는 둘 다 실수 및 허수 부분에서 형식의 일부에 속할 수 있는 두 복소수를 곱합니다.|  
|[operator \+](../Topic/operator+%20\(%3Ccomplex%3E\).md)|하나 또는 둘 다 실수 및 허수 부분에서 형식의 일부에 속할 수 있는 두 복소수를 더합니다.|  
|[연산자\-](../Topic/operator-%20\(%3Ccomplex%3E\)1.md)|하나 또는 둘 다 실수 및 허수 부분에서 형식의 일부에 속할 수 있는 두 복소수를 뺍니다.|  
|[operator\/](../Topic/operator-%20\(%3Ccomplex%3E\)2.md)|하나 또는 둘 다 실수 및 허수 부분에서 형식의 일부에 속할 수 있는 두 복소수를 나눕니다.|  
|[연산자 \<\<](../Topic/operator%3C%3C%20\(%3Ccomplex%3E\).md)|출력 스트림에 복소수를 삽입하는 템플릿 함수입니다.|  
|[연산자\=\=](../Topic/operator==%20\(%3Ccomplex%3E\).md)|하나 또는 둘 모두 실수 및 허수 부분에서 형식의 일부에 속할 수 있는 두 복소수를 같은지 테스트합니다.|  
|[연산자 \>\>](../Topic/operator%3E%3E%20\(%3Ccomplex%3E\).md)|입력 스트림에서 복소수를 추출하는 템플릿 함수입니다.|  
  
### 클래스  
  
|||  
|-|-|  
|[complex\<double\>](../standard-library/complex-double.md)|명시적으로 특수화된 템플릿 클래스는 둘 다 **double***,* 형식인 개체의 순서가 지정된 쌍을 저장하는 개체를 설명합니다. 첫 번째 개체는 복소수의 실수 부분을 나타내고 두 번째 개체는 허수 부분을 나타냅니다.|  
|[complex\<float\>](../standard-library/complex-float.md)|명시적으로 특수화된 템플릿 클래스는 둘 다 **float***,* 형식인 개체의 순서가 지정된 쌍을 저장하는 개체를 설명합니다. 첫 번째 개체는 복소수의 실수 부분을 나타내고 두 번째 개체는 허수 부분을 나타냅니다.|  
|[complex\<long double\>](../standard-library/complex-long-double.md)|명시적으로 특수화된 템플릿 클래스는 둘 다 `long double`*,* 형식인 개체의 순서가 지정된 쌍을 저장하는 개체를 설명합니다. 첫 번째 개체는 복소수의 실수 부분을 나타내고 두 번째 개체는 허수 부분을 나타냅니다.|  
|[대규모](../standard-library/complex-class.md)|이 템플릿 클래스는 복소수 체계를 나타내고 복잡한 산술 연산을 수행하는 데 사용되는 개체를 설명합니다.|  
  
### 리터럴  
 \<complex\> 헤더는 실수 부분이 0이 허수 부분이 입력 매개 변수의 값이 되는 복소수를 만드는 다음의 [사용자 정의 리터럴](../cpp/user-defined-literals-cpp.md)을 정의합니다.  
  
|||  
|-|-|  
|`constexpr complex<long double> operator""il(long double d)il(long double d)`<br /><br /> `constexpr complex<long double> operator""il(unsigned long long d)`|`complex<long double>{0.0L, static_cast<long double>(d)}`를 반환합니다.|  
|`constexpr complex<double> operator""i(long double d)`<br /><br /> `constexpr complex<double> operator""i(unsigned long long d)`|`complex<double>{0.0, static_cast<double>(d)}`를 반환합니다.|  
|`constexpr complex<float> operator""if(long double d)`<br /><br /> `constexpr complex<float> operator""if(unsigned long long d)`|`complex<float>{0.0f, static_cast<float>(d)}`를 반환합니다.|  
  
## 참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)