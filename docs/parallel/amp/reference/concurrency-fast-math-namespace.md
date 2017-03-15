---
title: "Concurrency:: fast_math Namespace | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp_math/Concurrency::fast_math
dev_langs:
- C++
ms.assetid: 54fed939-9902-49db-9f29-e98fd9821508
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 293452bf0a01f7f83a8a41bcb511bc57c9d45f26
ms.lasthandoff: 02/24/2017

---
# <a name="concurrencyfastmath-namespace"></a>Concurrency::fast_math 네임스페이스
가 작동 하는 `fast_math` 네임 스페이스는 정확도 단일 정밀도만 지원 (`float`), DirectX 내장 함수를 호출 합니다. 예를 들어, 각 함수에 두 개는 `cos` 및 `cosf`합니다. 두 버전 모두 하 고 반환 된 `float`, 하지만 각 호출에 동일한 DirectX 내장 함수입니다.  
  
## <a name="syntax"></a>구문  
  
```  
namespace fast_math;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="functions"></a>함수  
  
|이름|설명|  
|----------|-----------------|  
|[cos 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#cos)|인수의 아크코사인 값을 계산합니다.|  
|[cosf 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#cosf)|인수의 아크코사인 값을 계산합니다.|  
|[asin 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#asin)|인수의 아크사인 값을 계산합니다.|  
|[asinf 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#asinf)|인수의 아크사인 값을 계산합니다.|  
|[atan 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#atan)|인수의 아크탄젠트를 계산합니다.|  
|[atan2 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#atan2)|_Y/_X의 아크탄젠트를 계산합니다.|  
|[atan2f 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#atan2f)|_Y/_X의 아크탄젠트를 계산합니다.|  
|[atanf 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#atanf)|인수의 아크탄젠트를 계산합니다.|  
|[ceil 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#ceil)|인수의 한계를 계산합니다.|  
|[ceilf 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#ceilf)|인수의 한계를 계산합니다.|  
|[cos 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#cos)|인수의 코사인을 계산합니다.|  
|[cosf 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#cosf)|인수의 코사인을 계산합니다.|  
|[cosh 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#cosh)|인수의 하이퍼볼릭 코사인 값을 계산합니다.|  
|[coshf 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#coshf)|인수의 하이퍼볼릭 코사인 값을 계산합니다.|  
|[exp 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#exp)|밑이 e 인 인수의 지 수를 계산합니다.|  
|[exp2 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#exp2)|밑이&2; 인 인수의 지 수를 계산합니다.|  
|[exp2f 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#exp2f)|밑이&2; 인 인수의 지 수를 계산합니다.|  
|[expf 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#expf)|밑이 e 인 인수의 지 수를 계산합니다.|  
|[fabs 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#fabs)|인수의 절대값을 반환합니다.|  
|[fabsf 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#fabsf)|인수의 절대값을 반환합니다.|  
|[floor 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#floor)|인수의 밑을 계산합니다.|  
|[floorf 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#floorf)|인수의 밑을 계산합니다.|  
|[fmax 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#fmax)|인수의 최대 숫자 값 결정|  
|[fmaxf 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#fmaxf)|인수의 최대 숫자 값 결정|  
|[fmin 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#fmin)|인수의 최소 숫자 값 결정|  
|[fminf 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#fminf)|인수의 최소 숫자 값 결정|  
|[fmod 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#fmod)|_X/_Y의 부동 소수점 나머지 계산|  
|[fmodf 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#fmodf)|_X/_Y의 부동 소수점 나머지 계산|  
|[frexp 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#frexp)|가 수 및 _X의 지 수를 가져옵니다.|  
|[frexpf 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#frexpf)|가 수 및 _X의 지 수를 가져옵니다.|  
|[isfinite 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#isfinite)|인수가 유한 인 값인에 있는지 여부를 결정 합니다.|  
|[isinf 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#isinf)|인수가 무한대 인지 결정 합니다.|  
|[isnan 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#isnan)|인수가 NaN 인지 결정 합니다.|  
|[ldexp 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#ldexp)|가 수 및 지 수에서 숫자는 실수를 계산합니다.|  
|[ldexpf 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#ldexpf)|가 수 및 지 수에서 숫자는 실수를 계산합니다.|  
|[log 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#log)|인수의 밑이 e 인 로그 계산|  
|[log10 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#log10)|인수의 밑이&10; 인 로그 계산|  
|[log10f 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#log10f)|인수의 밑이&10; 인 로그 계산|  
|[log2 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#log2)|인수의 밑이&2; 인 로그 계산|  
|[log2f 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#log2f)|인수의 밑이&2; 인 로그 계산|  
|[logf 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#logf)|인수의 밑이 e 인 로그 계산|  
|[modf 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#modf)|정수 부분과 소수 부분에 _X 분할합니다.|  
|[modff 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#modff)|정수 부분과 소수 부분에 _X 분할합니다.|  
|[pow 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#pow)|_X _y 거듭제곱을 계산 합니다.|  
|[powf 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#powf)|_X _y 거듭제곱을 계산 합니다.|  
|[round 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#round)|_X 가장 가까운 정수로 반올림 합니다.|  
|[roundf 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#roundf)|_X 가장 가까운 정수로 반올림 합니다.|  
|[rsqrt 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#rsqrt)|역 인수의 제곱근을 반환합니다.|  
|[rsqrtf 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#rsqrtf)|역 인수의 제곱근을 반환합니다.|  
|[signbit 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#signbit)|인수의 부호를 반환 합니다.|  
|[signbitf 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#signbitf)|인수의 부호를 반환 합니다.|  
|[sin 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#sin)|인수의 사인 값을 계산합니다.|  
|[sincos 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#sincos)|_X의 사인 및 코사인 값을 계산합니다.|  
|[sincosf 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#sincosf)|_X의 사인 및 코사인 값을 계산합니다.|  
|[sinf 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#sinf)|인수의 사인 값을 계산합니다.|  
|[sinh 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#sinh)|인수의 하이퍼볼릭 사인 값을 계산합니다.|  
|[sinhf 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#sinhf)|인수의 하이퍼볼릭 사인 값을 계산합니다.|  
|[sqrt 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#sqrt)|인수의 제곱근을 계산합니다.|  
|[sqrtf 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#sqrtf)|인수의 제곱근을 계산합니다.|  
|[tan 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#tan)|인수의 탄젠트 값을 계산합니다.|  
|[tanf 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#tanf)|인수의 탄젠트 값을 계산합니다.|  
|[tanh 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#tanh)|인수의 하이퍼볼릭 탄젠트 값을 계산합니다.|  
|[tanhf 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#tanhf)|인수의 하이퍼볼릭 탄젠트 값을 계산합니다.|  
|[trunc 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#trunc)|정수 구성 요소에 대 한 인수를 자릅니다.|  
|[truncf 함수 (fast_math)](concurrency-fast-math-namespace-functions.md#truncf)|정수 구성 요소에 대 한 인수를 자릅니다.|  

## <a name="requirements"></a>요구 사항  
 **헤더:** amp_math.h  
  
 **Namespace:** concurrency:: fast_math  
  
## <a name="see-also"></a>참고 항목  
 [동시성 Namespace (c + + AMP)](concurrency-namespace-cpp-amp.md)

