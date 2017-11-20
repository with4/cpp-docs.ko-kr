---
title: "fmod, fmodf | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- fmod
- fmodf
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
- fmod
- _fmodl
- fmodf
dev_langs: C++
helpviewer_keywords:
- calculating floating-point remainders
- fmodf function
- fmod function
- floating-point numbers, calculating remainders
ms.assetid: 6962d369-d11f-40b1-a6d7-6f67239f8a23
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c6a53a704e14c3c8f8e022398b16e002c33c8328
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="fmod-fmodf"></a>fmod, fmodf
부동 소수점 나머지를 계산합니다.  
  
## <a name="syntax"></a>구문  
  
```  
double fmod(   
   double x,  
   double y   
);  
float fmod(  
   float x,  
   float y   
);  // C++ only  
long double fmod(  
   long double x,  
   long double y  
);  // C++ only  
float fmodf(   
   float x,  
   float y   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `x`, `y`  
 부동 소수점 값입니다.  
  
## <a name="return-value"></a>반환 값  
 `fmod`는 `x` / `y`의 부동 소수점 나머지를 반환합니다. `y`의 값이 0.0인 경우 `fmod`는 자동 NaN을 반환합니다. `printf` 패밀리에 의한 자동 NaN 표현에 대한 자세한 내용은 [printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)를 참조하세요.  
  
## <a name="remarks"></a>설명  
 `fmod` 함수는 `x` / `y`의 부동 소수점 나머지 `f`를 계산합니다(예: `x` = `i` `*` `y` + `f`). 여기서 `i`는 정수이고, `f`의 부호는 `x`와 같고, `f`의 절대값은 `y`의 절대값보다 작습니다.  
  
 C++에서는 오버로딩을 허용하므로 `fmod`의 오버로드를 호출할 수 있습니다. C 프로그램에서 `fmod`는 항상 double 값 두 개를 사용하며 double 값 하나를 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|함수|필수 헤더|  
|--------------|---------------------|  
|`fmod`, `fmodf`|\<math.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```  
// crt_fmod.c  
// This program displays a floating-point remainder.  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double w = -10.0, x = 3.0, z;  
  
   z = fmod( w, x );  
   printf( "The remainder of %.2f / %.2f is %f\n", w, x, z );  
}  
```  
  
```Output  
The remainder of -10.00 / 3.00 is -1.000000  
```  
  
## <a name="see-also"></a>참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [ceil, ceilf, ceill](../../c-runtime-library/reference/ceil-ceilf-ceill.md)   
 [fabs, fabsf, fabsl](../../c-runtime-library/reference/fabs-fabsf-fabsl.md)   
 [floor, floorf, floorl](../../c-runtime-library/reference/floor-floorf-floorl.md)   
 [_CIfmod](../../c-runtime-library/cifmod.md)