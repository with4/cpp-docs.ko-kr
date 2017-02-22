---
title: "Concurrency::fast_math 네임스페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amp_math/Concurrency::fast_math"
dev_langs: 
  - "C++"
ms.assetid: 54fed939-9902-49db-9f29-e98fd9821508
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Concurrency::fast_math 네임스페이스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`fast_math` 네임스페이스의 함수는 정확성이 낮으며, 단정밀도\(`float`\)를 지원하며, DirectX 내장 함수를 호출합니다.  예를 들어 `cos` 및 `cosf`와 같이 각 함수에는 두 가지 버전이 있습니다.  두 버전 모두 `float`를 사용하고 반환하지만 각각 동일한 DirectX 내장 함수를 호출합니다.  
  
## 구문  
  
```  
namespace fast_math;  
```  
  
## 멤버  
  
### 함수  
  
|Name|설명|  
|----------|--------|  
|[cos 함수\(fast\_math\)](../Topic/cos%20Function%20%20\(fast_math\).md)|인수의 아크코사인을 계산합니다.|  
|[cosf 함수\(fast\_math\)](../Topic/cosf%20Function%20\(fast_math\).md)|인수의 아크코사인을 계산합니다.|  
|[asin 함수\(fast\_math\)](../Topic/asin%20Function%20\(fast_math\).md)|인수의 아크사인을 계산합니다.|  
|[asinf 함수\(fast\_math\)](../Topic/asinf%20Function%20\(fast_math\).md)|인수의 아크사인을 계산합니다.|  
|[atan 함수\(fast\_math\)](../Topic/atan%20Function%20\(fast_math\).md)|인수의 아크탄젠트를 계산합니다.|  
|[atan2 함수\(fast\_math\)](../Topic/atan2%20Function%20\(fast_math\).md)|\_Y\/\_X의 아크탄젠트를 계산합니다.|  
|[atan2f 함수\(fast\_math\)](../Topic/atan2f%20Function%20\(fast_math\).md)|\_Y\/\_X의 아크탄젠트를 계산합니다.|  
|[atanf 함수\(fast\_math\)](../Topic/atanf%20Function%20\(fast_math\).md)|인수의 아크탄젠트를 계산합니다.|  
|[ceil 함수\(fast\_math\)](../Topic/ceil%20Function%20\(fast_math\).md)|인수의 한계를 계산합니다.|  
|[ceilf 함수\(fast\_math\)](../Topic/ceilf%20Function%20\(fast_math\).md)|인수의 한계를 계산합니다.|  
|[cos 함수\(fast\_math\)](../Topic/cos%20Function%20%20\(fast_math\).md)|인수의 코사인을 계산합니다.|  
|[cosf 함수\(fast\_math\)](../Topic/cosf%20Function%20\(fast_math\).md)|인수의 코사인을 계산합니다.|  
|[cosh 함수\(fast\_math\)](../Topic/cosh%20Function%20\(fast_math\).md)|인수의 하이퍼볼릭 코사인 값을 계산합니다.|  
|[coshf 함수\(fast\_math\)](../Topic/coshf%20Function%20\(fast_math\).md)|인수의 하이퍼볼릭 코사인 값을 계산합니다.|  
|[exp 함수\(fast\_math\)](../Topic/exp%20Function%20\(fast_math\).md)|인수의 밑이 e인 지수 값을 계산합니다.|  
|[exp2 함수\(fast\_math\)](../Topic/exp2%20Function%20\(fast_math\).md)|인수의 밑이 2인 지수 값을 계산합니다.|  
|[exp2f 함수\(fast\_math\)](../Topic/exp2f%20Function%20\(fast_math\).md)|인수의 밑이 2인 지수 값을 계산합니다.|  
|[expf 함수\(fast\_math\)](../Topic/expf%20Function%20\(fast_math\).md)|인수의 밑이 e인 지수 값을 계산합니다.|  
|[fabs 함수\(fast\_math\)](../Topic/fabs%20Function%20\(fast_math\).md)|인수의 절대 값을 반환합니다.|  
|[fabsf 함수\(fast\_math\)](../Topic/fabsf%20Function%20\(fast_math\).md)|인수의 절대 값을 반환합니다.|  
|[floor 함수\(fast\_math\)](../Topic/floor%20Function%20\(fast_math\).md)|인수의 밑을 계산합니다.|  
|[floorf 함수\(fast\_math\)](../Topic/floorf%20Function%20\(fast_math\).md)|인수의 밑을 계산합니다.|  
|[fmax 함수\(fast\_math\)](../Topic/fmax%20Function%20\(fast_math\).md)|인수의 최대 숫자 값을 확인합니다.|  
|[fmaxf 함수\(fast\_math\)](../Topic/fmaxf%20Function%20\(fast_math\).md)|인수의 최대 숫자 값을 확인합니다.|  
|[fmin 함수\(fast\_math\)](../Topic/fmin%20Function%20\(fast_math\).md)|인수의 최소 숫자 값을 확인합니다.|  
|[fminf 함수\(fast\_math\)](../Topic/fminf%20Function%20\(fast_math\).md)|인수의 최소 숫자 값을 확인합니다.|  
|[fmod 함수\(fast\_math\)](../Topic/fmod%20Function%20\(fast_math\).md)|\_X\/\_Y의 부동 소수점 나머지를 계산합니다.|  
|[fmodf 함수\(fast\_math\)](../Topic/fmodf%20Function%20\(fast_math\).md)|\_X\/\_Y의 부동 소수점 나머지를 계산합니다.|  
|[frexp 함수\(fast\_math\)](../Topic/frexp%20Function%20\(fast_math\).md)|\_X의 가수와 지수를 가져옵니다.|  
|[frexpf 함수\(fast\_math\)](../Topic/frexpf%20Function%20\(fast_math\).md)|\_X의 가수와 지수를 가져옵니다.|  
|[isfinite 함수\(fast\_math\)](../Topic/isfinite%20Function%20\(fast_math\).md)|인수에 유한한 값이 있는지 여부를 결정합니다.|  
|[isinf 함수\(fast\_math\)](../Topic/isinf%20Function%20\(fast_math\).md)|인수가 무한대인지 여부를 확인합니다.|  
|[isnan 함수\(fast\_math\)](../Topic/isnan%20Function%20\(fast_math\).md)|인수가 NaN인지 여부를 확인합니다.|  
|[ldexp 함수\(fast\_math\)](../Topic/ldexp%20Function%20\(fast_math\).md)|가수 및 지수에서 실수를 계산합니다.|  
|[ldexpf 함수\(fast\_math\)](../Topic/ldexpf%20Function%20\(fast_math\).md)|가수 및 지수에서 실수를 계산합니다.|  
|[log 함수\(fast\_math\)](../Topic/log%20Function%20\(fast_math\).md)|인수의 밑이 e인 로그 값을 계산합니다.|  
|[log10 함수\(fast\_math\)](../Topic/log10%20Function%20\(fast_math\).md)|인수의 밑이 10인 로그 값을 계산합니다.|  
|[log10f 함수\(fast\_math\)](../Topic/log10f%20Function%20\(fast_math\).md)|인수의 밑이 10인 로그 값을 계산합니다.|  
|[log2 함수\(fast\_math\)](../Topic/log2%20Function%20\(fast_math\).md)|인수의 상용 로그를 계산합니다.|  
|[log2f 함수\(fast\_math\)](../Topic/log2f%20Function%20\(fast_math\).md)|인수의 상용 로그를 계산합니다.|  
|[logf 함수\(fast\_math\)](../Topic/logf%20Function%20\(fast_math\).md)|인수의 밑이 e인 로그 값을 계산합니다.|  
|[modf 함수\(fast\_math\)](../Topic/modf%20Function%20\(fast_math\).md)|\_X를 소수 및 정수 부분으로 분할합니다.|  
|[modff 함수\(fast\_math\)](../Topic/modff%20Function%20\(fast_math\).md)|\_X를 소수 및 정수 부분으로 분할합니다.|  
|[pow 함수\(fast\_math\)](../Topic/pow%20Function%20\(fast_math\).md)|\_X의 \_Y 승을 계산합니다.|  
|[powf 함수\(fast\_math\)](../Topic/powf%20Function%20\(fast_math\).md)|\_X의 \_Y 승을 계산합니다.|  
|[round 함수\(fast\_math\)](../Topic/round%20Function%20\(fast_math\).md)|\_X를 가장 근접한 정수로 반올림합니다.|  
|[roundf 함수\(fast\_math\)](../Topic/roundf%20Function%20\(fast_math\).md)|\_X를 가장 근접한 정수로 반올림합니다.|  
|[rsqrt 함수\(fast\_math\)](../Topic/rsqrt%20Function%20\(fast_math\).md)|인수의 제곱근의 역수를 반환합니다.|  
|[rsqrtf 함수\(fast\_math\)](../Topic/rsqrtf%20Function%20\(fast_math\).md)|인수의 제곱근의 역수를 반환합니다.|  
|[signbit 함수\(fast\_math\)](../Topic/signbit%20Function%20\(fast_math\).md)|인수의 기호를 반환합니다.|  
|[signbitf 함수\(fast\_math\)](../Topic/signbitf%20Function%20\(fast_math\).md)|인수의 기호를 반환합니다.|  
|[sin 함수\(fast\_math\)](../Topic/sin%20Function%20\(fast_math\).md)|인수의 사인 값을 계산합니다.|  
|[sincos 함수\(fast\_math\)](../Topic/sincos%20Function%20\(fast_math\).md)|\_X의 사인 및 코사인 값을 계산합니다.|  
|[sincosf 함수\(fast\_math\)](../Topic/sincosf%20Function%20\(fast_math\).md)|\_X의 사인 및 코사인 값을 계산합니다.|  
|[sinf 함수\(fast\_math\)](../Topic/sinf%20Function%20\(fast_math\).md)|인수의 사인 값을 계산합니다.|  
|[sinh 함수\(fast\_math\)](../Topic/sinh%20Function%20\(fast_math\).md)|인수의 하이퍼볼릭 사인 값을 계산합니다.|  
|[sinhf 함수\(fast\_math\)](../Topic/sinhf%20Function%20\(fast_math\).md)|인수의 하이퍼볼릭 사인 값을 계산합니다.|  
|[sqrt 함수\(fast\_math\)](../Topic/sqrt%20Function%20\(fast_math\).md)|인수의 제곱근을 계산합니다.|  
|[sqrtf 함수\(fast\_math\)](../Topic/sqrtf%20Function%20\(fast_math\).md)|인수의 제곱근을 계산합니다.|  
|[tan 함수\(fast\_math\)](../Topic/tan%20Function%20\(fast_math\).md)|인수의 탄젠트 값을 계산합니다.|  
|[tanf 함수\(fast\_math\)](../Topic/tanf%20Function%20\(fast_math\).md)|인수의 탄젠트 값을 계산합니다.|  
|[tanh 함수\(fast\_math\)](../Topic/tanh%20Function%20\(fast_math\).md)|인수의 하이퍼볼릭 탄젠트 값을 계산합니다.|  
|[tanhf 함수\(fast\_math\)](../Topic/tanhf%20Function%20\(fast_math\).md)|인수의 하이퍼볼릭 탄젠트 값을 계산합니다.|  
|[trunc 함수\(fast\_math\)](../Topic/trunc%20Function%20\(fast_math\).md)|인수를 정수 구성 요소로 잘라냄|  
|[truncf 함수\(fast\_math\)](../Topic/truncf%20Function%20\(fast_math\).md)|인수를 정수 구성 요소로 잘라냄|  
  
## 요구 사항  
 **헤더:** amp\_math.h  
  
 **네임스페이스:** Concurrency::fast\_math  
  
## 참고 항목  
 [Concurrency 네임스페이스\(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)