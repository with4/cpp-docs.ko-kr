---
title: "exp, expf, 탐색 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- expf
- expl
- exp
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
- _expl
- expf
- expl
- exp
dev_langs:
- C++
helpviewer_keywords:
- exponential calculations
- expf function
- expl function
- calculating exponentials
- exp function
ms.assetid: 7070016d-1143-407e-9e9a-6b059bb88867
caps.latest.revision: 13
author: corob-msft
ms.author: corob
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: bce9249134b9d0e3716d8b79a0bc0642c64fc5e6
ms.contentlocale: ko-kr
ms.lasthandoff: 04/01/2017

---
# <a name="exp-expf-expl"></a>exp, expf, 탐색
지수를 계산합니다.  
  
## <a name="syntax"></a>구문  
  
```  
double exp(   
   double x  
);  
float exp(  
   float x  
);  // C++ only  
long double exp(  
   long double x  
);  // C++ only  
float expf(   
   float x  
);  
long double expl(  
   long double x  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 `x`  
 부동 소수점 값을 exponentiate 자연 로그 자료 *e* 여 합니다.  
  
## <a name="return-value"></a>반환 값  
 `exp` 부동 소수점 매개 변수를 지 수 값을 반환 하는 함수 *x*성공 하는 경우, 합니다. 즉, 결과 *e*<sup>*x*</sup>여기서 *e* 는 자연 로그의 기본 인터페이스입니다. 오버플로 함수 반환 값 (무한대) INF 및 언더플로, `exp` 0을 반환 합니다.  
  
|입력|SEH 예외|Matherr 예외|  
|-----------|-------------------|-----------------------|  
|± Quiet NaN, 비활성화|없음|_DOMAIN|  
|± 무한대|INVALID|_DOMAIN|  
|x ≥ 7.097827e+002|INEXACT+OVERFLOW|OVERFLOW|  
|X ≤ -7.083964e+002|INEXACT+UNDERFLOW|UNDERFLOW|  
  
 `exp` 함수에 스트리밍 SIMD 확장명 2 (SSE2)를 사용 하는 구현 합니다. SSE2 구현의 사용 제한 사항 및 사용 방법에 대한 자세한 내용은 [_set_SSE2_enable](../../c-runtime-library/reference/set-sse2-enable.md)을 참조하세요.  
  
## <a name="remarks"></a>설명  
 C + + 오버 로드의 오버 로드를 호출할 수 있도록 허용 `exp` 사용 하는 **float** 또는 **long double** 인수입니다. C 프로그램에서 `exp` 항상 사용 하 고 반환 된 **double**합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|함수|필수 C 헤더|필수 C++ 헤더|  
|--------------|---------------------|---|  
|`exp`, `expf`|\<math.h>|\<cmath> 또는 \<math.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```  
// crt_exp.c  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x = 2.302585093, y;  
  
   y = exp( x );  
   printf( "exp( %f ) = %f\n", x, y );  
}  
```  
  
```Output  
exp( 2.302585 ) = 10.000000  
```  
  
## <a name="see-also"></a>참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [log, logf, log10, log10f](../../c-runtime-library/reference/log-logf-log10-log10f.md)   
 [_CIexp](../../c-runtime-library/ciexp.md)
