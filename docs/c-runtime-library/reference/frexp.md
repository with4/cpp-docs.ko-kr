---
title: "frexp | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- frexp
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
- frexp
- _frexpl
dev_langs:
- C++
helpviewer_keywords:
- _frexpl function
- mantissas, floating-point variables
- frexpl function
- exponent, floating-point numbers
- frexp function
- floating-point functions, mantissa and exponent
ms.assetid: 9b020f2e-3967-45ec-a6a8-d467a071aa55
caps.latest.revision: 13
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
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: c281f59ebf90030abf2046e8639135aa47fc6058
ms.contentlocale: ko-kr
ms.lasthandoff: 03/30/2017

---
# <a name="frexp"></a>frexp
부동 소수점 숫자의 가수 및 지수를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
double frexp(  
   double x,  
   int *expptr   
);  
float frexp(  
   float x,  
   int * expptr  
);  // C++ only  
long double frexp(  
   long double x,  
   int * expptr  
);  // C++ only  
```  
  
#### <a name="parameters"></a>매개 변수  
 `x`  
 부동 소수점 값입니다.  
  
 `expptr`  
 저장된 정수 지수에 대한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 `frexp`는 가수를 반환합니다. `x`가 0이면 이 함수는 가수 및 지수에 대해 둘 다 0을 반환합니다. `expptr`가 `NULL`인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용한 경우 이 함수는 `errno`를 `EINVAL` 로 설정하고 0을 반환합니다.  
  
## <a name="remarks"></a>설명  
 `frexp` 함수는 부동 소수점 값(`x`)을 가수(`m`) 및 지수(`n`)으로 분할하므로, `m`의 절대값은 0.5보다 크거나 같고 1.0보다 작으며 `x` = `m`*2<sup>n</sup>입니다. 정수 지수 `n`은 `expptr`가 가리키는 위치에 저장됩니다.  
  
 C++에서는 오버로딩을 허용하므로 `frexp`의 오버로드를 호출할 수 있습니다. C 프로그램에서 `frexp`는 항상 double 및 정수를 사용하며 double을 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|함수|필수 헤더|  
|--------------|---------------------|  
|`frexp`|\<math.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```  
// crt_frexp.c  
// This program calculates frexp( 16.4, &n )  
// then displays y and n.  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x, y;  
   int n;  
  
   x = 16.4;  
   y = frexp( x, &n );  
   printf( "frexp( %f, &n ) = %f, n = %d\n", x, y, n );  
}  
```  
  
```Output  
frexp( 16.400000, &n ) = 0.512500, n = 5  
```  
  
## <a name="see-also"></a>참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [ldexp](../../c-runtime-library/reference/ldexp.md)   
 [modf, modff, modfl](../../c-runtime-library/reference/modf-modff-modfl.md)
