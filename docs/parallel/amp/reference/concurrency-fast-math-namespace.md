---
title: 'Concurrency:: fast_math Namespace | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: amp_math/Concurrency::fast_math
dev_langs: C++
ms.assetid: 54fed939-9902-49db-9f29-e98fd9821508
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 047eee60eb409e86d77faf6f637a88a56f271094
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="concurrencyfastmath-namespace"></a>Concurrency::fast_math 네임스페이스
함수는 `fast_math` 네임 스페이스는 정확도 단일 정밀도만 지원 (`float`), DirectX 내장 함수를 호출 합니다. 두 가지 버전 각 함수의 예를 들어 `cos` 및 `cosf`합니다. 두 버전 모두 사용 하 고 반환 된 `float`, 하지만 동일한 DirectX 호출 각각 내장 함수입니다.  
  
## <a name="syntax"></a>구문  
  
```  
namespace fast_math;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="functions"></a>함수  
  
|이름|설명|  
|----------|-----------------|  
|[cos](concurrency-fast-math-namespace-functions.md#cos)|인수의 아크코사인 값을 계산합니다.|  
|[cosf](concurrency-fast-math-namespace-functions.md#cosf)|인수의 아크코사인 값을 계산합니다.|  
|[asin](concurrency-fast-math-namespace-functions.md#asin)|인수의 아크사인 계산|  
|[asinf](concurrency-fast-math-namespace-functions.md#asinf)|인수의 아크사인 계산|  
|[atan](concurrency-fast-math-namespace-functions.md#atan)|인수의 아크탄젠트를 계산합니다.|  
|[atan2](concurrency-fast-math-namespace-functions.md#atan2)|_Y/_X의 아크탄젠트를 계산합니다.|  
|[atan2f](concurrency-fast-math-namespace-functions.md#atan2f)|_Y/_X의 아크탄젠트를 계산합니다.|  
|[atanf](concurrency-fast-math-namespace-functions.md#atanf)|인수의 아크탄젠트를 계산합니다.|  
|[ceil](concurrency-fast-math-namespace-functions.md#ceil)|인수의 한계를 계산합니다.|  
|[ceilf](concurrency-fast-math-namespace-functions.md#ceilf)|인수의 한계를 계산합니다.|  
|[cos](concurrency-fast-math-namespace-functions.md#cos)|인수의 코사인 값을 계산합니다.|  
|[cosf](concurrency-fast-math-namespace-functions.md#cosf)|인수의 코사인 값을 계산합니다.|  
|[cosh](concurrency-fast-math-namespace-functions.md#cosh)|인수의 하이퍼볼릭 코사인 값을 계산합니다.|  
|[coshf](concurrency-fast-math-namespace-functions.md#coshf)|인수의 하이퍼볼릭 코사인 값을 계산합니다.|  
|[exp](concurrency-fast-math-namespace-functions.md#exp)|밑이 e 인 인수를 계산합니다.|  
|[exp2](concurrency-fast-math-namespace-functions.md#exp2)|밑이 2 인 지 수의 인수를 계산합니다.|  
|[exp2f](concurrency-fast-math-namespace-functions.md#exp2f)|밑이 2 인 지 수의 인수를 계산합니다.|  
|[expf](concurrency-fast-math-namespace-functions.md#expf)|밑이 e 인 인수를 계산합니다.|  
|[fabs](concurrency-fast-math-namespace-functions.md#fabs)|인수의 절대값을 반환합니다.|  
|[fabsf](concurrency-fast-math-namespace-functions.md#fabsf)|인수의 절대값을 반환합니다.|  
|[floor](concurrency-fast-math-namespace-functions.md#floor)|인수의 밑을 계산합니다.|  
|[floorf](concurrency-fast-math-namespace-functions.md#floorf)|인수의 밑을 계산합니다.|  
|[fmax](concurrency-fast-math-namespace-functions.md#fmax)|인수의 최대 숫자 값을 결정|  
|[fmaxf](concurrency-fast-math-namespace-functions.md#fmaxf)|인수의 최대 숫자 값을 결정|  
|[fmin](concurrency-fast-math-namespace-functions.md#fmin)|인수의 숫자의 최소값 결정|  
|[fminf](concurrency-fast-math-namespace-functions.md#fminf)|인수의 숫자의 최소값 결정|  
|[fmod](concurrency-fast-math-namespace-functions.md#fmod)|_X/_Y의 부동 소수점 나머지 계산|  
|[fmodf](concurrency-fast-math-namespace-functions.md#fmodf)|_X/_Y의 부동 소수점 나머지 계산|  
|[frexp](concurrency-fast-math-namespace-functions.md#frexp)|가 수 및 _X의 지 수를 가져옵니다.|  
|[frexpf](concurrency-fast-math-namespace-functions.md#frexpf)|가 수 및 _X의 지 수를 가져옵니다.|  
|[isfinite](concurrency-fast-math-namespace-functions.md#isfinite)|인수가 유한 인 값인에 있는지 여부를 결정 합니다.|  
|[isinf](concurrency-fast-math-namespace-functions.md#isinf)|인수가 무한대 인지를 결정 합니다.|  
|[isnan](concurrency-fast-math-namespace-functions.md#isnan)|인수가 NaN 인지 확인 합니다.|  
|[ldexp](concurrency-fast-math-namespace-functions.md#ldexp)|가 수 및 지 수에서 실수를 계산합니다.|  
|[ldexpf](concurrency-fast-math-namespace-functions.md#ldexpf)|가 수 및 지 수에서 실수를 계산합니다.|  
|[log](concurrency-fast-math-namespace-functions.md#log)|인수의 밑이 e 인 지 수 로그를 계산합니다.|  
|[log10](concurrency-fast-math-namespace-functions.md#log10)|인수의 밑이 10 인 로그 계산|  
|[log10f](concurrency-fast-math-namespace-functions.md#log10f)|인수의 밑이 10 인 로그 계산|  
|[log2](concurrency-fast-math-namespace-functions.md#log2)|인수의 밑이 2 인 로그 계산|  
|[log2f](concurrency-fast-math-namespace-functions.md#log2f)|인수의 밑이 2 인 로그 계산|  
|[logf](concurrency-fast-math-namespace-functions.md#logf)|인수의 밑이 e 인 지 수 로그를 계산합니다.|  
|[modf](concurrency-fast-math-namespace-functions.md#modf)|정수 부분과 소수 부분에 _X를 분할합니다.|  
|[modff](concurrency-fast-math-namespace-functions.md#modff)|정수 부분과 소수 부분에 _X를 분할합니다.|  
|[pow](concurrency-fast-math-namespace-functions.md#pow)|_X _Y 거듭제곱을 계산 합니다.|  
|[powf](concurrency-fast-math-namespace-functions.md#powf)|_X _Y 거듭제곱을 계산 합니다.|  
|[round](concurrency-fast-math-namespace-functions.md#round)|_X 가장 가까운 정수로 반올림 합니다.|  
|[roundf](concurrency-fast-math-namespace-functions.md#roundf)|_X 가장 가까운 정수로 반올림 합니다.|  
|[rsqrt](concurrency-fast-math-namespace-functions.md#rsqrt)|역 인수의 제곱근을 반환합니다.|  
|[rsqrtf](concurrency-fast-math-namespace-functions.md#rsqrtf)|역 인수의 제곱근을 반환합니다.|  
|[signbit](concurrency-fast-math-namespace-functions.md#signbit)|인수의 부호를 반환합니다.|  
|[signbitf](concurrency-fast-math-namespace-functions.md#signbitf)|인수의 부호를 반환합니다.|  
|[sin](concurrency-fast-math-namespace-functions.md#sin)|인수의 사인 값을 계산합니다.|  
|[sincos](concurrency-fast-math-namespace-functions.md#sincos)|_X의 사인 값 및 코사인 값을 계산|  
|[sincosf](concurrency-fast-math-namespace-functions.md#sincosf)|_X의 사인 값 및 코사인 값을 계산|  
|[sinf](concurrency-fast-math-namespace-functions.md#sinf)|인수의 사인 값을 계산합니다.|  
|[sinh](concurrency-fast-math-namespace-functions.md#sinh)|인수의 하이퍼볼릭 사인 값을 계산합니다.|  
|[sinhf](concurrency-fast-math-namespace-functions.md#sinhf)|인수의 하이퍼볼릭 사인 값을 계산합니다.|  
|[sqrt](concurrency-fast-math-namespace-functions.md#sqrt)|인수의 제곱근을 계산합니다.|  
|[sqrtf](concurrency-fast-math-namespace-functions.md#sqrtf)|인수의 제곱근을 계산합니다.|  
|[tan](concurrency-fast-math-namespace-functions.md#tan)|인수의 탄젠트 값을 계산|  
|[tanf](concurrency-fast-math-namespace-functions.md#tanf)|인수의 탄젠트 값을 계산|  
|[tanh](concurrency-fast-math-namespace-functions.md#tanh)|인수의 하이퍼볼릭 탄젠트 값을 계산합니다.|  
|[tanhf](concurrency-fast-math-namespace-functions.md#tanhf)|인수의 하이퍼볼릭 탄젠트 값을 계산합니다.|  
|[trunc](concurrency-fast-math-namespace-functions.md#trunc)|정수 구성 요소에 대 한 인수를 자릅니다.|  
|[truncf](concurrency-fast-math-namespace-functions.md#truncf)|정수 구성 요소에 대 한 인수를 자릅니다.|  

## <a name="requirements"></a>요구 사항  
 **헤더:** amp_math.h  
  
 **Namespace:** concurrency:: fast_math  
  
## <a name="see-also"></a>참고 항목  
 [Concurrency 네임스페이스(C++ AMP)](concurrency-namespace-cpp-amp.md)
