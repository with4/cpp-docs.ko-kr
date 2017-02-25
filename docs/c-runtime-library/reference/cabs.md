---
title: "_cabs | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_cabs"
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
  - "cabsl"
  - "_cabs"
  - "_cabsl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_cabs 함수"
  - "_cabsl 함수"
  - "절대 값"
  - "cabs 함수"
  - "cabsl 함수"
  - "절대값 계산"
ms.assetid: fea292ee-1a39-4a0a-b416-4a189346ff26
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# _cabs
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

복소수의 절대값을 계산합니다.  
  
## 구문  
  
```  
double _cabs(   
   struct _complex z   
);  
```  
  
#### 매개 변수  
 `z`  
 복소수입니다.  
  
## 반환 값  
 `_cabs` 는 성공 하면 인수의 절대 값을 반환 합니다.  오버플로우에서, `_cabs` 는 `HUGE_VAL` 를 반환하고 `errno` 을 `ERANGE` 로 설정합니다.  오류처리를 [\_matherr](../../c-runtime-library/reference/matherr.md)을 사용하여 변경할 수 잇습니다.  
  
## 설명  
 이 `_cabs` 함수는 복잡한 숫자의 절대값을 계산합니다, 이는 형식 [\_complex](../../c-runtime-library/standard-types.md) 의 구조체여야 합니다.  구조체 `z` 는 실제 구성 요소인 `x` 와 허구의 구성요소 `y` 으로 이루어져 있습니다.  이러한 `_cabs` 에 대한 호출은 값을 생성합니다. 이 값은 `sqrt`\( `z.x``*``z.x` `+` `z.y` \* `z.y` 표현의 동일한 값입니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_cabs`|\<math.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_cabs.c  
/* Using _cabs, this program calculates  
 * the absolute value of a complex number.  
 */  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   struct _complex number = { 3.0, 4.0 };  
   double d;  
  
   d = _cabs( number );  
   printf( "The absolute value of %f + %fi is %f\n",  
           number.x, number.y, d );  
}  
```  
  
  **3.000000 \+ 4.000000i의 절대값은 5.000000**   
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [abs, labs, llabs \_abs64](../../c-runtime-library/reference/abs-labs-llabs-abs64.md)   
 [fabs, fabsf, fabsl](../../c-runtime-library/reference/fabs-fabsf-fabsl.md)   
 [labs, llabs](../../misc/labs-llabs.md)