---
title: "Concurrency:: precise_math Namespace | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp_math/Concurrency::precise_math
dev_langs:
- C++
ms.assetid: ba653308-dc28-4384-b2fd-6cd718a72f91
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: b64bd3e3702701ae2685d6688d88988dd91dc5d0
ms.lasthandoff: 02/24/2017

---
# <a name="concurrencyprecisemath-namespace"></a>Concurrency::precise_math 네임스페이스
가 작동 하는 `precise_math` 네임 스페이스 C99 호환 됩니다. 전체 자릿수 단일 및 이중 정밀도 버전의 각 함수가 포함 됩니다. 예를 들어 `acos` 은 이중 정밀도 버전 및 `acosf` 단 정밀도 버전입니다. 단 정밀도 함수를 포함 하 여 이러한 함수는 액셀러레이터에서 연장된 배정밀 지원이 필요 합니다. 사용할 수는 [accelerator:: supports_double_precision 데이터 멤버](accelerator-class.md#supports_double_precision) 특정 가속기에서 이러한 함수를 실행할 수 있는지 확인 하려면. 

  
## <a name="syntax"></a>구문  
  
```cpp  
namespace precise_math;  
```  
  
#### <a name="parameters"></a>매개 변수  
  
## <a name="members"></a>멤버  
  
### <a name="functions"></a>함수  
  
|이름|설명|  
|----------|-----------------|  
|[acos 함수](concurrency-precise-math-namespace-functions.md#acos)|오버로드됨. 인수의 아크코사인 값을 계산합니다.|  
|[acosf 함수](concurrency-precise-math-namespace-functions.md#acosf)|인수의 아크코사인 값을 계산합니다.|  
|[acosh 함수](concurrency-precise-math-namespace-functions.md#acosh)|오버로드됨. 인수의 역 하이퍼볼릭 코사인 값을 계산합니다.|  
|[acoshf 함수](concurrency-precise-math-namespace-functions.md#acoshf)|인수의 역 하이퍼볼릭 코사인 값을 계산합니다.|  
|[asin 함수](concurrency-precise-math-namespace-functions.md#asin)|오버로드됨. 인수의 아크사인 값을 계산합니다.|  
|[asinf 함수](concurrency-precise-math-namespace-functions.md#asinf)|인수의 아크사인 값을 계산합니다.|  
|[asinh 함수](concurrency-precise-math-namespace-functions.md#asinh)|오버로드됨. 인수의 역 하이퍼볼릭 사인 값을 계산합니다.|  
|[asinhf 함수](concurrency-precise-math-namespace-functions.md#asinhf)|인수의 역 하이퍼볼릭 사인 값을 계산합니다.|  
|[atan 함수](concurrency-precise-math-namespace-functions.md#atan)|오버로드됨. 인수의 아크탄젠트를 계산합니다.|  
|[atan2 함수](concurrency-precise-math-namespace-functions.md#atan2)|오버로드됨. _Y/_X의 아크탄젠트를 계산합니다.|  
|[atan2f 함수](concurrency-precise-math-namespace-functions.md#atan2f)|_Y/_X의 아크탄젠트를 계산합니다.|  
|[atanf 함수](concurrency-precise-math-namespace-functions.md#atanf)|인수의 아크탄젠트를 계산합니다.|  
|[atanh 함수](concurrency-precise-math-namespace-functions.md#atanh)|오버로드됨. 인수의 역 하이퍼볼릭 탄젠트 값을 계산합니다.|  
|[atanhf 함수](concurrency-precise-math-namespace-functions.md#atanhf)|인수의 역 하이퍼볼릭 탄젠트 값을 계산합니다.|  
|[cbrt 함수](concurrency-precise-math-namespace-functions.md#cbrt)|오버로드됨. 인수의 실제 세제곱근을 계산|  
|[cbrtf 함수](concurrency-precise-math-namespace-functions.md#cbrtf)|인수의 실제 세제곱근을 계산|  
|[ceil 함수](concurrency-precise-math-namespace-functions.md#ceil)|오버로드됨. 인수의 한계를 계산합니다.|  
|[ceilf 함수](concurrency-precise-math-namespace-functions.md#ceilf)|인수의 한계를 계산합니다.|  
|[copysign 함수](concurrency-precise-math-namespace-functions.md#copysign)|오버로드됨. _X 크기 및 _Y 부호 값을 생성합니다.|  
|[copysignf 함수](concurrency-precise-math-namespace-functions.md#copysignf)|_X 크기 및 _Y 부호 값을 생성합니다.|  
|[cos 함수](concurrency-precise-math-namespace-functions.md#cos)|오버로드됨. 인수의 코사인을 계산합니다.|  
|[cosf 함수](concurrency-precise-math-namespace-functions.md#cosf)|인수의 코사인을 계산합니다.|  
|[cosh 함수](concurrency-precise-math-namespace-functions.md#cosh)|오버로드됨. 인수의 하이퍼볼릭 코사인 값을 계산합니다.|  
|[coshf 함수](concurrency-precise-math-namespace-functions.md#coshf)|인수의 하이퍼볼릭 코사인 값을 계산합니다.|  
|[cospi 함수](concurrency-precise-math-namespace-functions.md#cospi)|오버로드됨. pi * _X의 코사인 값을 계산합니다.|  
|[cospif 함수](concurrency-precise-math-namespace-functions.md#cospif)|pi * _X의 코사인 값을 계산합니다.|  
|[erf 함수](concurrency-precise-math-namespace-functions.md#erf)|오버로드됨. _X의 오류 함수 계산|  
|[erfc 함수](concurrency-precise-math-namespace-functions.md#erfc)|오버로드됨. _X의 상보 오류 함수 계산|  
|[erfcf 함수](concurrency-precise-math-namespace-functions.md#erfcf)|_X의 상보 오류 함수 계산|  
|[erfcinv 함수](concurrency-precise-math-namespace-functions.md#erfcinv)|오버로드됨. _X의 역 상보 오류 함수 계산|  
|[erfcinvf 함수](concurrency-precise-math-namespace-functions.md#erfcinvf)|_X의 역 상보 오류 함수 계산|  
|[erff 함수](concurrency-precise-math-namespace-functions.md#erff)|_X의 오류 함수 계산|  
|[erfinv 함수](concurrency-precise-math-namespace-functions.md#erfinv)|오버로드됨. _X의 역 오류 함수 계산|  
|[erfinvf 함수](concurrency-precise-math-namespace-functions.md#erfinvf)|_X의 역 오류 함수 계산|  
|[exp 함수](concurrency-precise-math-namespace-functions.md#exp)|오버로드됨. 밑이 e 인 인수의 지 수를 계산합니다.|  
|[exp10 함수](concurrency-precise-math-namespace-functions.md#exp10)|오버로드됨. 밑수&10; 인수의 지 수를 계산합니다.|  
|[exp10f 함수](concurrency-precise-math-namespace-functions.md#exp10f)|밑수&10; 인수의 지 수를 계산합니다.|  
|[exp2 함수](concurrency-precise-math-namespace-functions.md#exp2)|오버로드됨. 밑이&2; 인 인수의 지 수를 계산합니다.|  
|[exp2f 함수](concurrency-precise-math-namespace-functions.md#exp2f)|밑이&2; 인 인수의 지 수를 계산합니다.|  
|[expf 함수](concurrency-precise-math-namespace-functions.md#expf)|밑이 e 인 인수의 지 수를 계산합니다.|  
|[expm1 함수](concurrency-precise-math-namespace-functions.md#expm1)|오버로드됨. 인수의 밑이 e인 지수 값 - 1을 계산합니다.|  
|[expm1f 함수](concurrency-precise-math-namespace-functions.md#expm1f)|인수의 밑이 e인 지수 값 - 1을 계산합니다.|  
|[fabs 함수](concurrency-precise-math-namespace-functions.md#fabs)|오버로드됨. 인수의 절대값을 반환합니다.|  
|[fabsf 함수](concurrency-precise-math-namespace-functions.md#fabsf)|인수의 절대값을 반환합니다.|  
|[fdim 함수](concurrency-precise-math-namespace-functions.md#fdim)|오버로드됨. 인수 사이의 양의 차이 결정합니다.|  
|[fdimf 함수](concurrency-precise-math-namespace-functions.md#fdimf)|인수 사이의 양의 차이 결정합니다.|  
|[floor 함수](concurrency-precise-math-namespace-functions.md#floor)|오버로드됨. 인수의 밑을 계산합니다.|  
|[floorf 함수](concurrency-precise-math-namespace-functions.md#floorf)|인수의 밑을 계산합니다.|  
|[fma 함수](concurrency-precise-math-namespace-functions.md#fma)|오버로드됨. 계산 (_X * _Y) +&3; 진 하나의 작업으로 반올림 _Z|  
|[fmaf 함수](concurrency-precise-math-namespace-functions.md#fmaf)|계산 (_X * _Y) +&3; 진 하나의 작업으로 반올림 _Z|  
|[fmax 함수](concurrency-precise-math-namespace-functions.md#fmax)|오버로드됨. 인수의 최대 숫자 값 결정|  
|[fmaxf 함수](concurrency-precise-math-namespace-functions.md#fmaxf)|인수의 최대 숫자 값 결정|  
|[fmin 함수](concurrency-precise-math-namespace-functions.md#fmin)|오버로드됨. 인수의 최소 숫자 값 결정|  
|[fminf 함수](concurrency-precise-math-namespace-functions.md#fminf)|인수의 최소 숫자 값 결정|  
|[fmod 함수 (c + + AMP)](concurrency-precise-math-namespace-functions.md#fmod)|오버로드됨. _X/_Y의 부동 소수점 나머지 계산|  
|[fmodf 함수](concurrency-precise-math-namespace-functions.md#fmodf)|_X/_Y의 부동 소수점 나머지 계산|  
|[fpclassify 함수](concurrency-precise-math-namespace-functions.md#fpclassify)|오버로드됨. 인수 값을 NaN, infinite, normal, subnormal,&0;으로 분류합니다.|  
|[frexp 함수](concurrency-precise-math-namespace-functions.md#frexp)|오버로드됨. 가 수 및 _X의 지 수를 가져옵니다.|  
|[frexpf 함수](concurrency-precise-math-namespace-functions.md#frexpf)|가 수 및 _X의 지 수를 가져옵니다.|  
|[hypot 함수](concurrency-precise-math-namespace-functions.md#hypot)|오버로드됨. _X 및 _Y 제곱합의 제곱근 계산|  
|[hypotf 함수](concurrency-precise-math-namespace-functions.md#hypotf)|_X 및 _Y 제곱합의 제곱근 계산|  
|[ilogb 함수](concurrency-precise-math-namespace-functions.md#ilogb)|오버로드됨. 부호 있는 정수 값으로 _X 지수를 추출합니다.|  
|[ilogbf 함수](concurrency-precise-math-namespace-functions.md#ilogbf)|부호 있는 정수 값으로 _X 지수를 추출합니다.|  
|[isfinite 함수](concurrency-precise-math-namespace-functions.md#isfinite)|오버로드됨. 인수가 유한 인 값인에 있는지 여부를 결정 합니다.|  
|[isinf 함수](concurrency-precise-math-namespace-functions.md#isinf)|오버로드됨. 인수가 무한대 인지 결정 합니다.|  
|[isnan 함수](concurrency-precise-math-namespace-functions.md#isnan)|오버로드됨. 인수가 NaN 인지 결정 합니다.|  
|[isnormal 함수](concurrency-precise-math-namespace-functions.md#isnormal)|오버로드됨. 인수가 정상인지 여부를 결정합니다.|  
|[ldexp 함수](concurrency-precise-math-namespace-functions.md#ldexp)|오버로드됨. 가 수 및 지 수에서 숫자는 실수를 계산합니다.|  
|[ldexpf 함수](concurrency-precise-math-namespace-functions.md#ldexpf)|가 수 및 지 수에서 숫자는 실수를 계산합니다.|  
|[lgamma 함수](concurrency-precise-math-namespace-functions.md#lgamma)|오버로드됨. 감마 인수의 절대 값 자연 로그 계산|  
|[lgammaf 함수](concurrency-precise-math-namespace-functions.md#lgammaf)|감마 인수의 절대 값 자연 로그 계산|  
|[log 함수](concurrency-precise-math-namespace-functions.md#log)|오버로드됨. 인수의 밑이 e 인 로그 계산|  
|[log10 함수](concurrency-precise-math-namespace-functions.md#log10)|오버로드됨. 인수의 밑이&10; 인 로그 계산|  
|[log10f 함수](concurrency-precise-math-namespace-functions.md#log10f)|인수의 밑이&10; 인 로그 계산|  
|[log1p 함수](concurrency-precise-math-namespace-functions.md#log1p)|오버로드됨. 인수에 1을 더한 값의 밑이 e인 로그 값을 계산합니다.|  
|[log1pf 함수](concurrency-precise-math-namespace-functions.md#log1pf)|인수에 1을 더한 값의 밑이 e인 로그 값을 계산합니다.|  
|[log2 함수](concurrency-precise-math-namespace-functions.md#log2)|오버로드됨. 인수의 밑이&2; 인 로그 계산|  
|[log2f 함수](concurrency-precise-math-namespace-functions.md#log2f)|인수의 밑이&2; 인 로그 계산|  
|[logb 함수](concurrency-precise-math-namespace-functions.md#logb)|오버로드됨. 부호 있는 정수 값으로서 _X의 지수를 부동 소수점 형식에서 추출합니다.|  
|[logbf 함수](concurrency-precise-math-namespace-functions.md#logbf)|부호 있는 정수 값으로서 _X의 지수를 부동 소수점 형식에서 추출합니다.|  
|[logf 함수](concurrency-precise-math-namespace-functions.md#logf)|인수의 밑이 e 인 로그 계산|  
|[modf 함수](concurrency-precise-math-namespace-functions.md#modf)|오버로드됨. 정수 부분과 소수 부분에 _X 분할합니다.|  
|[modff 함수](concurrency-precise-math-namespace-functions.md#modff)|정수 부분과 소수 부분에 _X 분할합니다.|  
|[nan 함수](concurrency-precise-math-namespace-functions.md#nan)|자동 NaN을 반환합니다.|  
|[nanf 함수](concurrency-precise-math-namespace-functions.md#nanf)|자동 NaN을 반환합니다.|  
|[nearbyint 함수](concurrency-precise-math-namespace-functions.md#nearbyint)|오버로드됨. 인수에 현재 반올림 방향을 사용하여 부동 소수점 형식에서 정수 값으로 반올림합니다.|  
|[nearbyintf 함수](concurrency-precise-math-namespace-functions.md#nearbyintf)|인수에 현재 반올림 방향을 사용하여 부동 소수점 형식에서 정수 값으로 반올림합니다.|  
|[nextafter 함수](concurrency-precise-math-namespace-functions.md#nextafter)|오버로드됨. _Y 방향에서 _X 후 유형의 함수에서 다음 표현 가능 값 결정|  
|[nextafterf 함수](concurrency-precise-math-namespace-functions.md#nextafterf)|_Y 방향에서 _X 후 유형의 함수에서 다음 표현 가능 값 결정|  
|[phi 함수](concurrency-precise-math-namespace-functions.md#phi)|오버로드됨. 인수는 누적 분포 함수를 반환합니다.|  
|[phif 함수](concurrency-precise-math-namespace-functions.md#phif)|인수는 누적 분포 함수를 반환합니다.|  
|[pow 함수](concurrency-precise-math-namespace-functions.md#pow)|오버로드됨. _X _y 거듭제곱을 계산 합니다.|  
|[powf 함수](concurrency-precise-math-namespace-functions.md#powf)|_X _y 거듭제곱을 계산 합니다.|  
|[probit 함수](concurrency-precise-math-namespace-functions.md#probit)|오버로드됨. 인수의 역 누적 분포 함수를 반환합니다.|  
|[probitf 함수](concurrency-precise-math-namespace-functions.md#probitf)|인수의 역 누적 분포 함수를 반환합니다.|  
|[rcbrt 함수](concurrency-precise-math-namespace-functions.md#rcbrt)|오버로드됨. 인수의 제곱근의 역을 반환합니다.|  
|[rcbrtf 함수](concurrency-precise-math-namespace-functions.md#rcbrtf)|인수의 제곱근의 역을 반환합니다.|  
|[remainder 함수](concurrency-precise-math-namespace-functions.md#remainder)|오버로드됨. 나머지 계산: _X REM _Y|  
|[remainderf 함수](concurrency-precise-math-namespace-functions.md#remainderf)|나머지 계산: _X REM _Y|  
|[remquo 함수](concurrency-precise-math-namespace-functions.md#remquo)|오버로드됨. 동일한 나머지 _X REM _Y를 계산합니다. 또한 정수 몫 _X/_Y의 하위 23 비트를 계산 하 고 같은 _X/_Y 부호 값을 제공 합니다. 지정 된 값이 _Quo 가리키는 정수에 저장 합니다.|  
|[remquof 함수](concurrency-precise-math-namespace-functions.md#remquof)|동일한 나머지 _X REM _Y를 계산합니다. 또한 정수 몫 _X/_Y의 하위 23 비트를 계산 하 고 같은 _X/_Y 부호 값을 제공 합니다. 지정 된 값이 _Quo 가리키는 정수에 저장 합니다.|  
|[round 함수](concurrency-precise-math-namespace-functions.md#round)|오버로드됨. _X 가장 가까운 정수로 반올림 합니다.|  
|[roundf 함수](concurrency-precise-math-namespace-functions.md#roundf)|_X 가장 가까운 정수로 반올림 합니다.|  
|[rsqrt 함수](concurrency-precise-math-namespace-functions.md#rsqrt)|오버로드됨. 역 인수의 제곱근을 반환합니다.|  
|[rsqrtf 함수](concurrency-precise-math-namespace-functions.md#rsqrtf)|역 인수의 제곱근을 반환합니다.|  
|[scalb 함수](concurrency-precise-math-namespace-functions.md#scalb)|오버로드됨. _X에 FLT_RADIX를 곱하여 _Y 거듭제곱을 구합니다.|  
|[scalbf 함수](concurrency-precise-math-namespace-functions.md#scalbf)|_X에 FLT_RADIX를 곱하여 _Y 거듭제곱을 구합니다.|  
|[scalbn 함수](concurrency-precise-math-namespace-functions.md#scalbn)|오버로드됨. _X에 FLT_RADIX를 곱하여 _Y 거듭제곱을 구합니다.|  
|[scalbnf 함수](concurrency-precise-math-namespace-functions.md#scalbnf)|_X에 FLT_RADIX를 곱하여 _Y 거듭제곱을 구합니다.|  
|[signbit 함수](concurrency-precise-math-namespace-functions.md#signbit)|오버로드됨. _X의 부호가 음수인지 결정합니다.|  
|[signbitf 함수](concurrency-precise-math-namespace-functions.md#signbitf)|_X의 부호가 음수인지 결정합니다.|  
|[sin 함수](concurrency-precise-math-namespace-functions.md#sin)|오버로드됨. 인수의 사인 값을 계산합니다.|  
|[sincos 함수](concurrency-precise-math-namespace-functions.md#sincos)|오버로드됨. _X의 사인 및 코사인 값을 계산합니다.|  
|[sincosf 함수](concurrency-precise-math-namespace-functions.md#sincosf)|_X의 사인 및 코사인 값을 계산합니다.|  
|[sinf 함수](concurrency-precise-math-namespace-functions.md#sinf)|인수의 사인 값을 계산합니다.|  
|[sinh 함수](concurrency-precise-math-namespace-functions.md#sinh)|오버로드됨. 인수의 하이퍼볼릭 사인 값을 계산합니다.|  
|[sinhf 함수](concurrency-precise-math-namespace-functions.md#sinhf)|인수의 하이퍼볼릭 사인 값을 계산합니다.|  
|[sinpi 함수](concurrency-precise-math-namespace-functions.md#sinpi)|오버로드됨. pi * _X의 사인 값을 계산합니다.|  
|[sinpif 함수](concurrency-precise-math-namespace-functions.md#sinpif)|pi * _X의 사인 값을 계산합니다.|  
|[sqrt 함수](concurrency-precise-math-namespace-functions.md#sqrt)|오버로드됨. 인수의 제곱근을 계산합니다.|  
|[sqrtf 함수](concurrency-precise-math-namespace-functions.md#sqrtf)|인수의 제곱근을 계산합니다.|  
|[tan 함수](concurrency-precise-math-namespace-functions.md#tan)|오버로드됨. 인수의 탄젠트 값을 계산합니다.|  
|[tanf 함수](concurrency-precise-math-namespace-functions.md#tanf)|인수의 탄젠트 값을 계산합니다.|  
|[tanh 함수](concurrency-precise-math-namespace-functions.md#tanh)|오버로드됨. 인수의 하이퍼볼릭 탄젠트 값을 계산합니다.|  
|[tanhf 함수](concurrency-precise-math-namespace-functions.md#tanhf)|인수의 하이퍼볼릭 탄젠트 값을 계산합니다.|  
|[tanpi 함수](concurrency-precise-math-namespace-functions.md#tanpi)|오버로드됨. pi * _X의 탄젠트 값을 계산합니다.|  
|[tanpif 함수](concurrency-precise-math-namespace-functions.md#tanpif)|pi * _X의 탄젠트 값을 계산합니다.|  
|[tgamma 함수](concurrency-precise-math-namespace-functions.md#tgamma)|오버로드됨. _X의 감마 함수 계산|  
|[tgammaf 함수](concurrency-precise-math-namespace-functions.md#tgammaf)|_X의 감마 함수 계산|  
|[trunc 함수](concurrency-precise-math-namespace-functions.md#trunc)|오버로드됨. 정수 구성 요소에 대 한 인수를 자릅니다.|  
|[truncf 함수](concurrency-precise-math-namespace-functions.md#truncf)|정수 구성 요소에 대 한 인수를 자릅니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** amp_math.h  
  
 **네임스페이스:** 동시성  
  
## <a name="see-also"></a>참고 항목  
 [동시성 Namespace (c + + AMP)](concurrency-namespace-cpp-amp.md)

