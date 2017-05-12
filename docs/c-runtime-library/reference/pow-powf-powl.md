---
title: pow, powf, powl | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- powl
- pow
- powf
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
- powl
- pow
- _powl
- powf
dev_langs:
- C++
helpviewer_keywords:
- exponential calculations
- powl function
- _powl function
- exponentiation
- powers, calculating
- calculating exponentials
- powf function
- pow function
ms.assetid: e75c33ed-2e59-48b1-be40-81da917324f1
caps.latest.revision: 18
author: corob-msft
ms.author: corob
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 4400582a792644b928c02db346bc7eae1087dc85
ms.contentlocale: ko-kr
ms.lasthandoff: 04/01/2017

---
# <a name="pow-powf-powl"></a>pow, powf, powl
`x` 의 `y`승 값을 계산합니다.  
  
## <a name="syntax"></a>구문  
  
```  
double pow(  
   double x,  
   double y   
);  
double pow(  
   double x,  
   int y  
);  // C++ only  
float pow(  
   float x,  
   float y   
);  // C++ only  
float pow(  
   float x,  
   int y  
);  // C++ only  
long double pow(  
   long double x,  
   long double y  
);  // C++ only  
long double pow(  
   long double x,  
   int y  
);  // C++ only  
float powf(  
   float x,  
   float y   
);  
long double powl(  
   long double x,  
   long double y  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `x`  
 밑입니다.  
  
 `y`  
 지수입니다.  
  
## <a name="return-value"></a>반환 값  
 `x`<sup>y</sup>의 값을 반환합니다. 오버플로 또는 언더플로 시 오류 메시지는 인쇄되지 않습니다.  
  
|x 및 y의 값|pow의 반환 값|  
|-----------------------|-------------------------|  
|`x` \< > 0 및 `y` = 0.0|1|  
|`x` = 0.0 및 `y` = 0.0|1|  
|`x` = 0.0 및 `y` < 0|INF|  
  
## <a name="remarks"></a>설명  
 `pow`는 `1.0E100`처럼 2<sup>64</sup>보다 큰 정수 부동 소수점 값을 인식하지 못합니다.  
  
 `pow`에는 SSE2(스트리밍 SIMD 확장 2)를 사용하는 구현이 있습니다. SSE2 구현의 사용 제한 사항 및 그 사용 방법에 대한 자세한 내용은 [_set_SSE2_enable](../../c-runtime-library/reference/set-sse2-enable.md)을 참조하세요.  
  
 C++에서는 오버로드를 허용하므로 `pow`의 여러 오버로드 중 원하는 항목을 호출할 수 있습니다. C 프로그램에서 `pow`는 항상 double 값 두 개를 사용하며 double 값 하나를 반환합니다.  
  
 `pow(int, int)` 오버로드는 더 이상 사용할 수 없습니다. 이 오버로드를 사용하는 경우 컴파일러에서 C2668을 내보낼 수 있습니다. 이 문제를 방지하려면 첫 번째 매개 변수를 `double`, `float` 또는 `long double`로 캐스팅합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`pow`, `powf`, `powl`|\<math.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="libraries"></a>라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## <a name="example"></a>예제  
  
```  
// crt_pow.c  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x = 2.0, y = 3.0, z;  
  
   z = pow( x, y );  
   printf( "%.1f to the power of %.1f is %.1f\n", x, y, z );  
}  
```  
  
## <a name="output"></a>출력  
  
```  
2.0 to the power of 3.0 is 8.0  
```  
  
## <a name="see-also"></a>참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [exp, expf, 탐색](../../c-runtime-library/reference/exp-expf.md)   
 [log, logf, log10, log10f](../../c-runtime-library/reference/log-logf-log10-log10f.md)   
 [sqrt, sqrtf, sqrtl](../../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)   
 [_CIpow](../../c-runtime-library/cipow.md)
