---
title: modf, modff, modfl | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- modff
- modf
- modfl
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
- modff
- _modfl
- modf
- modfl
- math/modf
- math/modff
- math/modfl
dev_langs: C++
helpviewer_keywords:
- modf function
- modff function
- modfl function
ms.assetid: b1c7abf5-d476-43ca-a03c-02072a86e32d
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a75cc474d66a42f3faeb7444f3168c7cc3283514
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="modf-modff-modfl"></a>modf, modff, modfl
부동 소수점 값을 소수 부분과 정수 부분으로 분할합니다.  
  
## <a name="syntax"></a>구문  
  
```  
double modf(  
   double x,  
   double * intptr   
);  
float modf(  
   float x,  
   float * intptr  
);  // C++ only  
long double modf(  
   long double x,  
   long double * intptr  
);  // C++ only  
float modff(  
   float x,  
   float * intptr   
);  
long double modfl(  
   long double x,  
   long double * intptr  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 *x*  
 부동 소수점 값입니다.  
  
 `intptr`  
 저장된 정수 부분에 대한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 이 함수는 *x*의 부호 있는 소수 부분을 반환합니다. 반환되는 오류가 없습니다.  
  
## <a name="remarks"></a>설명  
 `modf` 함수는 부동 소수점 값 `x`를 소수 부분과 정수 부분으로 분할합니다. 각 부분의 부호는 `x`와 같습니다. `x`의 부호 있는 소수 부분이 반환됩니다. 정수 부분은 `intptr.`에 부동 소수점 값으로 저장됩니다.  
  
 `modf`에는 SSE2(스트리밍 SIMD 확장 2)를 사용하는 구현이 있습니다. SSE2 구현의 사용 제한 사항 및 사용 방법에 대한 자세한 내용은 [_set_SSE2_enable](../../c-runtime-library/reference/set-sse2-enable.md)을 참조하세요.  
  
 C++에서는 오버로드를 허용하므로 `float` 또는 `long double` 매개 변수를 사용 및 반환하는 `modf`의 오버로드를 호출할 수 있습니다. C 프로그램에서 `modf`는 항상 double 값 두 개를 사용하며 double 값 하나를 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`modf`, `modff`, `modfl`|C: \<math.h><br /><br /> C++: , \<cmath> 또는 \<math.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## <a name="libraries"></a>라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## <a name="example"></a>예  
  
```  
// crt_modf.c  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x, y, n;  
  
   x = -14.87654321;      /* Divide x into its fractional */  
   y = modf( x, &n );     /* and integer parts            */  
  
   printf( "For %f, the fraction is %f and the integer is %.f\n",   
           x, y, n );  
}  
```  
  
## <a name="output"></a>출력  
  
```  
For -14.876543, the fraction is -0.876543 and the integer is -14  
```  
  
## <a name="see-also"></a>참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [frexp](../../c-runtime-library/reference/frexp.md)   
 [ldexp](../../c-runtime-library/reference/ldexp.md)