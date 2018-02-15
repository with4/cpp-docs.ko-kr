---
title: nextafter, nextafterf, nextafterl, _nextafter, _nextafterf, nexttoward, nexttowardf, nexttowardl | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- nextafterf
- _nextafterf
- nextafter
- nextafterl
- _nextafter
- nexttoward
- nexttowardf
- nexttowardl
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
- nextafter
- _nextafter
- nextafterf
- nextafterl
- _nextafterf
- math/nextafter
- math/nextafterf
- math/nextafterl
- nexttoward
- nexttowardf
- nexttowardl
- math/nexttoward
- math/nexttowardf
- math/nexttowardl
dev_langs:
- C++
helpviewer_keywords:
- _nextafter function
- nextafter function
- _nextafterf function
- nextafterf function
- nextafterl function
- nexttoward function
- nexttowardf function
- nexttowardl function
ms.assetid: 9785bfb9-de53-4bd0-9637-f05fa0c1f6ab
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a4fe078e00b28f09284f3b91ad93ee1393bea108
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="nextafter-nextafterf-nextafterl-nextafter-nextafterf-nexttoward-nexttowardf-nexttowardl"></a>nextafter, nextafterf, nextafterl, _nextafter, _nextafterf, nexttoward, nexttowardf, nexttowardl
표현 가능한 다음 부동 소수점 값을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
double nextafter(  
   double x,  
   double y   
);  
  
float nextafter(  
   float x,  
   float y   
); /* C++ only, requires <cmath> */  
  
long double nextafter(  
   long double x,  
   long double y   
); /* C++ only, requires <cmath> */  
  
float nextafterf(  
   float x,  
   float y   
);   
  
long double nextafterl(  
   long double x,  
   long double y   
);  
  
double _nextafter(  
   double x,  
   double y   
);  
  
float _nextafterf(  
   float x,  
   float y   
); /* x64 only */  
  
double nexttoward(  
   double x,  
   long double y   
);  
  
float nexttoward(  
   float x,  
   long double y   
); /* C++ only, requires <cmath> */  
  
long double nexttoward(  
   long double x,  
   long double y   
); /* C++ only, requires <cmath> */  
  
float nexttowardf(  
   float x,  
   long double y   
);   
  
long double nexttowardl(  
   long double x,  
   long double y   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `x`  
 시작할 부동 소수점 값입니다.  
  
 `y`  
 종료할 부동 소수점 값입니다.  
  
## <a name="return-value"></a>반환 값  
 `x` 이후 `y` 방향에 있는 반환 형식의 표현 가능한 다음 부동 소수점 값을 반환합니다. `x`=`y`인 경우 함수는 반환 형식으로 변환된 `y`를 반환하며 예외는 트리거되지 않습니다. `x`가 `y`와 같지 않으며 결과가 비정상적인 값이거나 0이면 FE_UNDERFLOW 및 FE_INEXACT 부동 소수점 예외 상태가 설정되며 올바른 값이 반환됩니다. `x` 또는 `y` 중 하나가 NAN이면 반환 값은 입력 NAN 중 하나가 됩니다. `x`가 유한값인데 결과는 무한값이거나 해당 형식으로 표현할 수 없는 경우에는 올바른 부호가 지정된 무한대 또는 NAN이 반환되고, FE_OVERFLOW 및 FE_INEXACT 부동 소수점 예외 상태가 설정되며, `errno`가 ERANGE로 설정됩니다.  
  
## <a name="remarks"></a>설명  
 `nextafter` 및 `nexttoward` 함수 패밀리는 `y`의 매개 변수 형식을 제외하면 동일합니다. `x`와 `y`가 같으면 반환되는 값은 반환 형식으로 변환된 `y`입니다.  
  
 C++에서는 오버로드를 허용하므로 \<cmath>를 포함하는 경우 `float` 및 `long double` 형식을 반환하는 `nextafter` 및 `nexttoward`의 오버로드를 호출할 수 있습니다. C 프로그램에서 `nextafter` 및 `nexttoward`가 항상 `double`을 반환합니다.  
  
 `_nextafter` 및 `_nextafterf` 함수는 Microsoft 전용입니다. `_nextafterf` 함수는 x64용으로 컴파일할 때만 사용 가능합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더(C)|필수 헤더(C++)|  
|-------------|---------------------------|-------------------------------|  
|`nextafter`, `nextafterf`, `nextafterl`, `_nextafterf`, `nexttoward`, `nexttowardf`, `nexttowardl`|\<math.h>|\<math.h> 또는 \<cmath>|  
|`_nextafter`|\<float.h>|\<float.h> 또는 \<cfloat>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [isnan, _isnan, _isnanf](../../c-runtime-library/reference/isnan-isnan-isnanf.md)