---
title: sqrt, sqrtf, sqrtl | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- sqrtl
- sqrtf
- sqrt
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
- sqrt
- sqrtf
- _sqrtl
dev_langs:
- C++
helpviewer_keywords:
- sqrtf function
- sqrt function
- sqrtl function
- _sqrtl function
- calculating square roots
- square roots, calculating
ms.assetid: 2ba9467b-f172-41dc-8f10-b86f68fa813c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 525e2414dd92ed486506fceedc6fb550b4a7a569
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="sqrt-sqrtf-sqrtl"></a>sqrt, sqrtf, sqrtl
제곱근을 계산합니다.  
  
## <a name="syntax"></a>구문  
  
```  
double sqrt(  
   double x   
);  
float sqrt(  
   float x   
);  // C++ only  
long double sqrt(  
   long double x  
);  // C++ only  
float sqrtf(  
   float x   
);  
long double sqrtl(  
   long double x   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `x`  
 음수가 아닌 부동 소수점 값  
  
## <a name="remarks"></a>설명  
 C++에서는 오버로드를 허용하므로 `sqrt` 또는 `float` 형식을 사용하는 `long double`의 오버로드를 호출할 수 있습니다. C 프로그램에서 `sqrt`는 항상 `double`을 사용 및 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 `sqrt` 함수는 `x`의 제곱근을 반환합니다. 기본적으로 `x`가 음수이면 `sqrt`는 무한 NaN을 반환합니다.  
  
|입력|SEH 예외|`_matherr` 예외|  
|-----------|-------------------|--------------------------|  
|± QNAN,IND|없음|_DOMAIN|  
|- ∞|없음|_DOMAIN|  
|x<0|없음|_DOMAIN|  
  
## <a name="requirements"></a>요구 사항  
  
|함수|C 헤더|C++ 헤더|  
|--------------|--------------|------------------|  
|`sqrt`, `sqrtf`, `sqrtl`|\<math.h>|\<cmath>|  
  
 호환성에 대한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예  
  
```C  
// crt_sqrt.c  
// This program calculates a square root.  
  
#include <math.h>  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   double question = 45.35, answer;  
   answer = sqrt( question );  
   if( question < 0 )  
      printf( "Error: sqrt returns %f\n", answer );  
   else  
      printf( "The square root of %.2f is %.2f\n", question, answer );  
}  
```  
  
```Output  
The square root of 45.35 is 6.73  
```  
  
## <a name="see-also"></a>참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [exp, expf, expl](../../c-runtime-library/reference/exp-expf.md)   
 [log, logf, log10, log10f](../../c-runtime-library/reference/log-logf-log10-log10f.md)   
 [pow, powf, powl](../../c-runtime-library/reference/pow-powf-powl.md)   
 [_CIsqrt](../../c-runtime-library/cisqrt.md)