---
title: nearbyint, nearbyintf, nearbyintl | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- nearbyint
- nearbyintf
- nerabyintl
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- nearbyint
- nearbyintf
- nearbyintl
- math/nearbyint
- math/narbyintf
- math/narbyintl
dev_langs:
- C++
helpviewer_keywords:
- nearbyint function
- nearbyintf function
- nearbyintl function
ms.assetid: dd39cb68-96b0-434b-820f-6ff2ea65584f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f6c4cce9fb5d95da5e65a064d622da22e4d0f0a8
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="nearbyint-nearbyintf-nearbyintl"></a>nearbyint, nearbyintf, nearbyintl
지정된 부동 소수점 값을 정수로 반올림하고 부동 소수점 형식으로 해당 값을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
double nearbyint(  
   double x  
);  
  
float nearbyint(  
   float x  
); //C++ only  
  
long double nearbyint(  
   long double x  
); //C++ only  
  
float nearbyintf(  
   float x  
);  
  
long double nearbyintl(  
   long double x  
);  
  
```  
  
#### <a name="parameters"></a>매개 변수  
 [in] `x`  
 반올림할 값입니다.  
  
## <a name="return-value"></a>반환 값  
 함수가 정상적으로 실행되면 fegetround로 정의된 현재 반올림 형식을 사용하여 가장 가까운 정수로 반올림된 `x`가 반환됩니다. 그렇지 않은 경우에는 함수가 다음 값 중 하나를 반환할 수 있습니다.  
  
|문제|반환|  
|-----------|------------|  
|`x` ±INFINITY =|수정 되지 않은 ±INFINITY|  
|`x` = ±0|수정 되지 않은 ±0|  
|`x` = NaN|NaN|  
  
 오류는 [_matherr](../../c-runtime-library/reference/matherr.md)을 통해 보고되지 않습니다. 구체적으로 설명하자면, 이 함수는 FE_INEXACT 예외를 보고하지 않습니다.  
  
## <a name="remarks"></a>설명  
 이 함수와 `rint`의 가장 큰 차이점은, 이 함수를 사용하는 경우 부정확한 부동 소수점 예외가 발생하지 않는다는 것입니다.  
  
 최대 부동 소수점 값은 정확한 정수이므로 이 함수 자체는 오버플로되지 않으며, 사용하는 함수의 버전에 따라 출력이 반환 값을 오버플로할 수는 있습니다.  
  
## <a name="requirements"></a>요구 사항  
  
|함수|C 헤더|C++ 헤더|  
|--------------|--------------|------------------|  
|`nearbyint`,                `nearbyintf`,  `nearbyintl`|\<math.h>|\<cmath>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [사전순 함수 참조](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)