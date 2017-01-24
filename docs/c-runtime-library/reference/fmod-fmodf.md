---
title: "fmod, fmodf | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "fmod"
  - "fmodf"
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
  - "fmod"
  - "_fmodl"
  - "fmodf"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "부동 소수점 나머지 계산"
  - "fmodf 함수"
  - "fmod 함수"
  - "부동 소수점 숫자, 나머지 계산"
ms.assetid: 6962d369-d11f-40b1-a6d7-6f67239f8a23
caps.latest.revision: 13
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# fmod, fmodf
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

부동 소수점 나머지를 계산합니다.  
  
## 구문  
  
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
  
#### 매개 변수  
 `x`, `y`  
 부동 소수점 값  
  
## 반환 값  
 `fmod`은 `x` \/ `y`의 부동 소수점 나머지를 반환합니다.  `y`의 값이 0.0인 경우 `fmod`이 quiet NaN을 반환합니다.  `printf` 제품군별 quiet NaN의 표현에 대한 자세한 정보는 [printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)를 참조하십시오.  
  
## 설명  
 `fmod` 함수는 `x` \= `i` `*` `y` \+ `f`로 수행되는 `x` \/ `y`의 부동 소수점 나머지 `f`를 계산합니다. 여기서 `i`는 정수이고 `f`에는 `x`와 같은 기호가 있으며 `f`의 절대값은 `y`의 절대값보다 작습니다.  
  
 C\+\+ 오버 로딩을 허용하여 오버 로드인 `fmod` 을 호출할 수 있습니다.  C 프로그램에서 `fmod`는 항상 2개의 double을 사용하고 하나의 double을 반환합니다.  
  
## 요구 사항  
  
|Function|필수 헤더|  
|--------------|-----------|  
|`fmod`, `fmodf`|\<math.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
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
  
  **\-10.00 \/ 3.00의 나머지는 \-1.000000입니다.**   
## 해당 .NET Framework 항목  
 [System::Math::IEEERemainder](https://msdn.microsoft.com/en-us/library/system.math.ieeeremainder.aspx)  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [ceil, ceilf, ceill](../../c-runtime-library/reference/ceil-ceilf-ceill.md)   
 [fabs, fabsf, fabsl](../../c-runtime-library/reference/fabs-fabsf-fabsl.md)   
 [floor, floorf, floorl](../../c-runtime-library/reference/floor-floorf-floorl.md)   
 [\_CIfmod](../../c-runtime-library/cifmod.md)