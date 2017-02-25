---
title: "Concurrency::precise_math 네임스페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amp_math/Concurrency::precise_math"
dev_langs: 
  - "C++"
ms.assetid: ba653308-dc28-4384-b2fd-6cd718a72f91
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Concurrency::precise_math 네임스페이스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`precise_math` 네임스페이스에 있는 함수는 C99 규격입니다.  각 함수의 단정밀도 버전 및 배정밀도 버전이 모두 포함되어 있습니다.  예를 들어, `acos` 는 이중 정밀도 버전 및  `acosf`  단정밀도 버전입니다.  단정밀도 기능을 포함하는 이러한 함수는 액셀러레이터에 대해 확장된 이중 정밀도 지원이 필요합니다.  특정 엑셀러레이터에서 이러한 함수를 실행할 수 있는지 확인 하려면 [accelerator::supports\_double\_precision 데이터 멤버](../Topic/accelerator::supports_double_precision%20Data%20Member.md) 를 사용할 수 있습니다.  
  
## 구문  
  
```vb  
namespace precise_math;  
```  
  
#### 매개 변수  
  
## 멤버  
  
### 함수  
  
|Name|설명|  
|----------|--------|  
|[acos 함수](../Topic/acos%20Function.md)|오버로드됨.  인수의 아크코사인을 계산합니다.|  
|[acosf 함수](../Topic/acosf%20Function.md)|인수의 아크코사인을 계산합니다.|  
|[acosh 함수](../Topic/acosh%20Function.md)|오버로드됨.  인수의 역 하이퍼볼릭 코사인 값을 계산합니다.|  
|[acoshf 함수](../Topic/acoshf%20Function.md)|인수의 역 하이퍼볼릭 코사인 값을 계산합니다.|  
|[asin 함수](../Topic/asin%20Function.md)|오버로드됨.  인수의 아크사인을 계산합니다.|  
|[asinf 함수](../Topic/asinf%20Function.md)|인수의 아크사인을 계산합니다.|  
|[asinh 함수](../Topic/asinh%20Function.md)|오버로드됨.  인수의 역 하이퍼볼릭 사인 값을 계산합니다.|  
|[asinhf 함수](../Topic/asinhf%20Function.md)|인수의 역 하이퍼볼릭 사인 값을 계산합니다.|  
|[atan 함수](../Topic/atan%20Function.md)|오버로드됨.  인수의 아크탄젠트를 계산합니다.|  
|[atan2 함수](../Topic/atan2%20Function.md)|오버로드됨.  \_Y\/\_X의 아크탄젠트를 계산합니다.|  
|[atan2f 함수](../Topic/atan2f%20Function.md)|\_Y\/\_X의 아크탄젠트를 계산합니다.|  
|[atanf 함수](../Topic/atanf%20Function.md)|인수의 아크탄젠트를 계산합니다.|  
|[atanh 함수](../Topic/atanh%20Function.md)|오버로드됨.  인수의 역 하이퍼볼릭 탄젠트 값을 계산합니다.|  
|[atanhf 함수](../Topic/atanhf%20Function.md)|인수의 역 하이퍼볼릭 탄젠트 값을 계산합니다.|  
|[cbrt 함수](../Topic/cbrt%20Function.md)|오버로드됨.  인수의 실제 세제곱근을 계산합니다.|  
|[cbrtf 함수](../Topic/cbrtf%20Function.md)|인수의 실제 세제곱근을 계산합니다.|  
|[ceil 함수](../Topic/ceil%20Function.md)|오버로드됨.  인수의 한계를 계산합니다.|  
|[ceilf 함수](../Topic/ceilf%20Function.md)|인수의 한계를 계산합니다.|  
|[copysign 함수](../Topic/copysign%20Function.md)|오버로드됨.  엄청난 \_X 및 \_Y의 부호 값을 생성합니다.|  
|[copysignf 함수](../Topic/copysignf%20Function.md)|엄청난 \_X 및 \_Y 부호 값을 생성합니다.|  
|[cos 함수](../Topic/cos%20Function.md)|오버로드됨.  인수의 코사인을 계산합니다.|  
|[cosf 함수](../Topic/cosf%20Function.md)|인수의 코사인을 계산합니다.|  
|[cosh 함수](../Topic/cosh%20Function.md)|오버로드됨.  인수의 하이퍼볼릭 코사인 값을 계산합니다.|  
|[coshf 함수](../Topic/coshf%20Function.md)|인수의 하이퍼볼릭 코사인 값을 계산합니다.|  
|[cospi 함수](../Topic/cospi%20Function.md)|오버로드됨.  pi \* \_X의 코사인 값을 계산합니다.|  
|[cospif 함수](../Topic/cospif%20Function.md)|pi \* \_X의 코사인 값을 계산합니다.|  
|[erf 함수](../Topic/erf%20Function.md)|오버로드됨.  \_X의 오차 함수를 계산합니다.|  
|[erfc 함수](../Topic/erfc%20Function.md)|오버로드됨.  \_X의 보완적인 오차 함수를 계산합니다.|  
|[erfcf 함수](../Topic/erfcf%20Function.md)|\_X의 보완적인 오차 함수를 계산합니다.|  
|[erfcinv 함수](../Topic/erfcinv%20Function.md)|오버로드됨.  \_X의 역 오차 함수를 계산합니다.|  
|[erfcinvf 함수](../Topic/erfcinvf%20Function.md)|\_X의 역 오차 함수를 계산합니다.|  
|[erff 함수](../Topic/erff%20Function.md)|\_X의 오차 함수를 계산합니다.|  
|[erfinv 함수](../Topic/erfinv%20Function.md)|오버로드됨.  \_X의 역 오차 함수를 계산합니다.|  
|[erfinvf 함수](../Topic/erfinvf%20Function.md)|\_X의 역 오차 함수를 계산합니다.|  
|[exp 함수](../Topic/exp%20Function.md)|오버로드됨.  인수의 밑이 e인 지수 값을 계산합니다.|  
|[exp10 함수](../Topic/exp10%20Function.md)|오버로드됨.  인수의 밑이 10인 지수 값을 계산합니다.|  
|[exp10f 함수](../Topic/exp10f%20Function.md)|인수의 밑이 10인 지수 값을 계산합니다.|  
|[exp2 함수](../Topic/exp2%20Function.md)|오버로드됨.  인수의 밑이 2인 지수 값을 계산합니다.|  
|[exp2f 함수](../Topic/exp2f%20Function.md)|인수의 밑이 2인 지수 값을 계산합니다.|  
|[expf 함수](../Topic/expf%20Function.md)|인수의 밑이 e인 지수 값을 계산합니다.|  
|[expm1 함수](../Topic/expm1%20Function.md)|오버로드됨.  인수\-1의 밑이 e인 지수 값을 계산합니다.|  
|[expm1f 함수](../Topic/expm1f%20Function.md)|인수\-1의 밑이 e인 지수 값을 계산합니다.|  
|[fabs 함수](../Topic/fabs%20Function.md)|오버로드됨.  인수의 절대 값을 반환합니다.|  
|[fabsf 함수](../Topic/fabsf%20Function.md)|인수의 절대 값을 반환합니다.|  
|[fdim 함수](../Topic/fdim%20Function.md)|오버로드됨.  인수 사이의 양의 차이를 결정합니다.|  
|[fdimf 함수](../Topic/fdimf%20Function.md)|인수 사이의 양의 차이를 결정합니다.|  
|[floor 함수](../Topic/floor%20Function.md)|오버로드됨.  인수의 밑을 계산합니다.|  
|[floorf 함수](../Topic/floorf%20Function.md)|인수의 밑을 계산합니다.|  
|[fma 함수](../Topic/fma%20Function.md)|오버로드됨.  \(\_X \* \_Y\) \+ \_Z를 하나의 삼항 연산으로 반올림하여 계산합니다.|  
|[fmaf 함수](../Topic/fmaf%20Function.md)|\(\_X \* \_Y\) \+ \_Z를 하나의 삼항 연산으로 반올림하여 계산합니다.|  
|[fmax 함수](../Topic/fmax%20Function.md)|오버로드됨.  인수의 최대 숫자 값을 확인합니다.|  
|[fmaxf 함수](../Topic/fmaxf%20Function.md)|인수의 최대 숫자 값을 확인합니다.|  
|[fmin 함수](../Topic/fmin%20Function.md)|오버로드됨.  인수의 최소 숫자 값을 확인합니다.|  
|[fminf 함수](../Topic/fminf%20Function.md)|인수의 최소 숫자 값을 확인합니다.|  
|[fmod 함수\(C\+\+ AMP\)](../Topic/fmod%20Function%20\(C++%20AMP\).md)|오버로드됨.  \_X\/\_Y의 부동 소수점 나머지를 계산합니다.|  
|[fmodf 함수](../Topic/fmodf%20Function.md)|\_X\/\_Y의 부동 소수점 나머지를 계산합니다.|  
|[fpclassify 함수](../Topic/fpclassify%20Function.md)|오버로드됨.  인수 값을 NaN, 무한, subnormal, 0으로 인수 값을 분류합니다.|  
|[frexp 함수](../Topic/frexp%20Function.md)|오버로드됨.  \_X의 가수와 지수를 가져옵니다.|  
|[frexpf 함수](../Topic/frexpf%20Function.md)|\_X의 가수와 지수를 가져옵니다.|  
|[hypot 함수](../Topic/hypot%20Function.md)|오버로드됨.  \_X 및 \_Y 제곱합의 제곱근을 계산합니다.|  
|[hypotf 함수](../Topic/hypotf%20Function.md)|\_X 및 \_Y 제곱합의 제곱근을 계산합니다.|  
|[ilogb 함수](../Topic/ilogb%20Function.md)|오버로드됨.  서명된 정수 값으로 \_X 지수를 추출합니다.|  
|[ilogbf 함수](../Topic/ilogbf%20Function.md)|서명된 정수 값으로 \_X 지수를 추출합니다.|  
|[isfinite 함수](../Topic/isfinite%20Function.md)|오버로드됨.  인수에 유한한 값이 있는지 여부를 결정합니다.|  
|[isinf 함수](../Topic/isinf%20Function.md)|오버로드됨.  인수가 무한대인지 여부를 확인합니다.|  
|[isnan 함수](../Topic/isnan%20Function.md)|오버로드됨.  인수가 NaN인지 여부를 확인합니다.|  
|[isnormal 함수](../Topic/isnormal%20Function.md)|오버로드됨.  인수가 정상인지 여부를 확인합니다.|  
|[ldexp 함수](../Topic/ldexp%20Function.md)|오버로드됨.  가수 및 지수에서 실수를 계산합니다.|  
|[ldexpf 함수](../Topic/ldexpf%20Function.md)|가수 및 지수에서 실수를 계산합니다.|  
|[lgamma 함수](../Topic/lgamma%20Function.md)|오버로드됨.  감마 인수의 절대 값의 자연 로그를 계산합니다.|  
|[lgammaf 함수](../Topic/lgammaf%20Function.md)|감마 인수의 절대 값의 자연 로그를 계산합니다.|  
|[log 함수](../Topic/log%20Function.md)|오버로드됨.  인수의 밑이 e인 로그 값을 계산합니다.|  
|[log10 함수](../Topic/log10%20Function.md)|오버로드됨.  인수의 밑이 10인 로그 값을 계산합니다.|  
|[log10f 함수](../Topic/log10f%20Function.md)|인수의 밑이 10인 로그 값을 계산합니다.|  
|[log1p 함수](../Topic/log1p%20Function.md)|오버로드됨.  인수에 1을 더한 값의 밑이 e인 로그 값을 계산합니다.|  
|[log1pf 함수](../Topic/log1pf%20Function.md)|인수에 1을 더한 값의 밑이 e인 로그 값을 계산합니다.|  
|[log2 함수](../Topic/log2%20Function.md)|오버로드됨.  인수의 상용 로그를 계산합니다.|  
|[log2f 함수](../Topic/log2f%20Function.md)|인수의 상용 로그를 계산합니다.|  
|[logb 함수](../Topic/logb%20Function.md)|오버로드됨.  부호화된 정수 값으로서 \_X의 지수를 부동 소수점 형식에서 추출합니다.|  
|[logbf 함수](../Topic/logbf%20Function.md)|부호화된 정수 값으로서 \_X의 지수를 부동 소수점 형식에서 추출합니다.|  
|[logf 함수](../Topic/logf%20Function.md)|인수의 밑이 e인 로그 값을 계산합니다.|  
|[modf 함수](../Topic/modf%20Function.md)|오버로드됨.  \_X를 소수 및 정수 부분으로 분할합니다.|  
|[modff 함수](../Topic/modff%20Function.md)|\_X를 소수 및 정수 부분으로 분할합니다.|  
|[nan 함수](../Topic/nan%20Function.md)|상당한 NaN을 반환합니다.|  
|[nanf 함수](../Topic/nanf%20Function.md)|상당한 NaN을 반환합니다.|  
|[nearbyint 함수](../Topic/nearbyint%20Function.md)|오버로드됨.  인수에 현재 반올림 방향을 사용하여 부동 소수점 형식에서 정수 값으로 반올림 합니다.|  
|[nearbyintf 함수](../Topic/nearbyintf%20Function.md)|인수에 현재 반올림 방향을 사용하여 부동 소수점 형식에서 정수 값으로 반올림 합니다.|  
|[nextafter 함수](../Topic/nextafter%20Function.md)|오버로드됨.  \_Y 방향으로 \_X 다음에 함수의 형식으로 다음에 표현이 가능한 값을 설명합니다.|  
|[nextafterf 함수](../Topic/nextafterf%20Function.md)|\_Y 방향으로 \_X 다음에 함수의 형식으로 다음에 표현이 가능한 값을 설명합니다.|  
|[phi 함수](../Topic/phi%20Function.md)|오버로드됨.  인수의 누적 분포 함수를 반환합니다.|  
|[phif 함수](../Topic/phif%20Function.md)|인수의 누적 분포 함수를 반환합니다.|  
|[pow 함수](../Topic/pow%20Function.md)|오버로드됨.  \_X의 \_Y 승을 계산합니다.|  
|[powf 함수](../Topic/powf%20Function.md)|\_X의 \_Y 승을 계산합니다.|  
|[probit 함수](../Topic/probit%20Function.md)|오버로드됨.  인수의 역 누적 분포 함수를 반환합니다.|  
|[probitf 함수](../Topic/probitf%20Function.md)|인수의 역 누적 분포 함수를 반환합니다.|  
|[rcbrt 함수](../Topic/rcbrt%20Function.md)|오버로드됨.  인수의 세제곱근의 역수를 반환합니다.|  
|[rcbrtf 함수](../Topic/rcbrtf%20Function.md)|인수의 세제곱근의 역수를 반환합니다.|  
|[remainder 함수](../Topic/remainder%20Function.md)|오버로드됨.  나머지를 계산합니다: \_X REM \_Y|  
|[remainderf 함수](../Topic/remainderf%20Function.md)|나머지를 계산합니다: \_X REM \_Y|  
|[remquo 함수](../Topic/remquo%20Function.md)|오버로드됨.  \_X REM \_Y와 같은 나머지를 계산 합니다.  또한 하위 23 비트의 정수 몫 \_X\/\_Y를 계산 하고 \_X\/\_Y 와 같은 부호의 값을 제공 합니다.  \_Quo가 가리키는 정수에 지정된 값이 저장 됩니다.|  
|[remquof 함수](../Topic/remquof%20Function.md)|\_X REM \_Y와 같은 나머지를 계산 합니다.  또한 하위 23 비트의 정수 몫 \_X\/\_Y를 계산 하고 \_X\/\_Y 와 같은 부호의 값을 제공 합니다.  \_Quo가 가리키는 정수에 지정된 값이 저장 됩니다.|  
|[round 함수](../Topic/round%20Function.md)|오버로드됨.  \_X를 가장 근접한 정수로 반올림합니다.|  
|[roundf 함수](../Topic/roundf%20Function.md)|\_X를 가장 근접한 정수로 반올림합니다.|  
|[rsqrt 함수](../Topic/rsqrt%20Function.md)|오버로드됨.  인수의 제곱근의 역수를 반환합니다.|  
|[rsqrtf 함수](../Topic/rsqrtf%20Function.md)|인수의 제곱근의 역수를 반환합니다.|  
|[scalb 함수](../Topic/scalb%20Function.md)|오버로드됨.  FLT\_RADIX에 의해 전원 \_Y에 \_X를 곱합니다.|  
|[scalbf 함수](../Topic/scalbf%20Function.md)|FLT\_RADIX에 의해 전원 \_Y에 \_X를 곱합니다.|  
|[scalbn 함수](../Topic/scalbn%20Function.md)|오버로드됨.  FLT\_RADIX에 의해 전원 \_Y에 \_X를 곱합니다.|  
|[scalbnf 함수](../Topic/scalbnf%20Function.md)|FLT\_RADIX에 의해 전원 \_Y에 \_X를 곱합니다.|  
|[signbit 함수](../Topic/signbit%20Function.md)|오버로드됨.  \_X의 부호가 음수인지 결정합니다.|  
|[signbitf 함수](../Topic/signbitf%20Function.md)|\_X의 부호가 음수인지 결정합니다.|  
|[sin 함수](../Topic/sin%20Function.md)|오버로드됨.  인수의 사인 값을 계산합니다.|  
|[sincos 함수](../Topic/sincos%20Function.md)|오버로드됨.  \_X의 사인 및 코사인 값을 계산합니다.|  
|[sincosf 함수](../Topic/sincosf%20Function.md)|\_X의 사인 및 코사인 값을 계산합니다.|  
|[sinf 함수](../Topic/sinf%20Function.md)|인수의 사인 값을 계산합니다.|  
|[sinh 함수](../Topic/sinh%20Function.md)|오버로드됨.  인수의 하이퍼볼릭 사인 값을 계산합니다.|  
|[sinhf 함수](../Topic/sinhf%20Function.md)|인수의 하이퍼볼릭 사인 값을 계산합니다.|  
|[sinpi 함수](../Topic/sinpi%20Function.md)|오버로드됨.  pi \* \_X의 사인 값을 계산합니다.|  
|[sinpif 함수](../Topic/sinpif%20Function.md)|pi \* \_X의 사인 값을 계산합니다.|  
|[sqrt 함수](../Topic/sqrt%20Function.md)|오버로드됨.  인수의 제곱근을 계산합니다.|  
|[sqrtf 함수](../Topic/sqrtf%20Function.md)|인수의 제곱근을 계산합니다.|  
|[tan 함수](../Topic/tan%20Function.md)|오버로드됨.  인수의 탄젠트 값을 계산합니다.|  
|[tanf 함수](../Topic/tanf%20Function.md)|인수의 탄젠트 값을 계산합니다.|  
|[tanh 함수](../Topic/tanh%20Function.md)|오버로드됨.  인수의 하이퍼볼릭 탄젠트 값을 계산합니다.|  
|[tanhf 함수](../Topic/tanhf%20Function.md)|인수의 하이퍼볼릭 탄젠트 값을 계산합니다.|  
|[tanpi 함수](../Topic/tanpi%20Function.md)|오버로드됨.  pi \* \_X의 탄젠트 값을 계산합니다.|  
|[tanpif 함수](../Topic/tanpif%20Function.md)|pi \* \_X의 탄젠트 값을 계산합니다.|  
|[tgamma 함수](../Topic/tgamma%20Function.md)|오버로드됨.  \_X의 감마 함수를 계산합니다.|  
|[tgammaf 함수](../Topic/tgammaf%20Function.md)|\_X의 감마 함수를 계산합니다.|  
|[trunc 함수](../Topic/trunc%20Function.md)|오버로드됨.  인수를 정수 구성 요소로 잘라냄|  
|[truncf 함수](../Topic/truncf%20Function.md)|인수를 정수 구성 요소로 잘라냄|  
  
## 요구 사항  
 **헤더:** amp\_math.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [Concurrency 네임스페이스\(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)