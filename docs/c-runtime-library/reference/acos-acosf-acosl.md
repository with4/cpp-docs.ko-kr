---
title: "acos, acosf, acosl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "acosf"
  - "acos"
  - "acosl"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-math-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "acos"
  - "acosl"
  - "acosf"
  - "math/acosf"
  - "math/acosl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "acos 함수"
  - "acosf 함수"
  - "acosl 함수"
  - "역 코사인 함수"
  - "삼각 함수"
ms.assetid: 00b89c48-8faf-4824-aa95-fa4349a4975d
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# acos, acosf, acosl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

아크코사인 값을 계산합니다.  
  
## 구문  
  
```  
double acos(   
   double x   
);  
float acos(  
   float x   
);   // C++ only  
long double acos(  
   long double x  
);   // C++ only  
float acosf(  
   float x   
);  
long double acosl(  
   long double x  
);  
```  
  
#### 매개 변수  
 `x`  
 \(역 코사인 값\) 값을 계산 하는 1 – 1 사이의 값입니다.  
  
## 반환 값  
 `acos` 의 아크코사인 값을 반환 하는 함수 `x` 0에서 π 라디안입니다.  
  
 기본적으로 경우 `x` \-1 보다 작거나 1 보다 큰 `acos` 는 무한을 반환 합니다.  
  
|입력|SEH 예외|Matherr 예외|  
|--------|------------|----------------|  
|± ∞|`INVALID`|`_DOMAIN`|  
|± QNAN,IND|없음|`_DOMAIN`|  
|&#124;x&#124;\>1|`INVALID`|`_DOMAIN`|  
  
## 설명  
 C\+\+가 오버로딩을 허용하기 때문에, `float` 와 `long double` 값을 사용하고 반환하는 `acos` 의 오버로드를 호출할 수 있습니다.  C 프로그램에서 `acos`는 항상 `double`을 사용하고 반환합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|선택적 헤더|  
|--------|-----------|------------|  
|`acos`, `acosf`, `acosl`|\<math.h\>|\<\<errno.h\>\>|  
  
## 예제  
 이 프로그램\-1에서 1 사이의 값을 묻는 메시지가 나타납니다.  입력 값이이 범위를 벗어나는 `_DOMAIN` 오류 메시지입니다.  유효한 값을 입력 하는 경우 프로그램 아크사인 값 및 해당 값의 아크코사인 값을 인쇄 합니다.  
  
```  
// crt_asincos.c  
// arguments: 0  
  
#include <math.h>  
#include <stdio.h>  
#include <stdlib.h>  
#include <errno.h>  
  
int main( int ac, char* av[] )  
{  
    double  x,  
            y;  
    errno_t err;   
  
    // argument checking  
    if (ac != 2)  
    {  
        fprintf_s( stderr, "Usage: %s <number between -1 and 1>\n",  
                   av[0]);  
        return 1;  
    }  
  
    // Convert argument into a double value  
    if ((err = sscanf_s( av[1], "%lf", &x )) != 1)  
    {  
        fprintf_s( stderr, "Error converting argument into ",  
                   "double value.\n");  
        return 1;  
    }  
  
    // Arcsine of X  
    y = asin( x );  
    printf_s( "Arcsine of %f = %f\n", x, y );  
  
    // Arccosine of X  
    y = acos( x );  
    printf_s( "Arccosine of %f = %f\n", x, y );  
}  
```  
  
  **0.000000 \= 0.000000 아크사인 값**  
**0.000000 \= 1.570796의 아크코사인 값**   
## 해당 .NET Framework 항목  
 [System::Math::Acos](https://msdn.microsoft.com/en-us/library/system.math.acos.aspx)  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [asin, asinf, asinl](../../c-runtime-library/reference/asin-asinf-asinl.md)   
 [atan, atanf, atanl, atan2, atan2f, atan2l](../../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)   
 [cos, cosf, cosl, cosh, coshf, coshl](../../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)   
 [\_matherr](../../c-runtime-library/reference/matherr.md)   
 [sin, sinf, sinl, sinh, sinhf, sinhl](../../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)   
 [tan, tanf, tanl, tanh, tanhf, tanhl](../../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)