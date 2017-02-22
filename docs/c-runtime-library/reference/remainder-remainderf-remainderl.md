---
title: "remainder, remainderf, remainderl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "remainderl"
  - "remainder"
  - "remainderf"
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
  - "remainderf"
  - "remainder"
  - "remainderl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "remainderf"
  - "remainderl"
  - "remainder"
ms.assetid: 5f721fb3-8b78-4597-9bc0-ca9bcd1f1d0e
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# remainder, remainderf, remainderl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

두 부동 소수점 값을 가장 가까운 정수 계열 값으로 반올림 몫의 나머지를 계산 합니다.  
  
## 구문  
  
```  
double remainder(   
   double numer,  
   double denom  
);  
float remainder(   
   float numer,  
   float denom  
); /* C++ only */  
long double remainder(   
   long double numer,  
   long double denom  
); /* C++ only */  
float remainderf(   
   float numer,  
   float denom  
);  
long double remainderl(   
   long double numer,  
   long double denom  
);  
  
```  
  
#### 매개 변수  
 `numer`  
 분자입니다.  
  
 `denom`  
 분모입니다.  
  
## 반환 값  
 `x` \/ `y`의 나머지 부동 소수점입니다.  `y`의 값이 0.0인 경우 `remainder`이 quiet NaN을 반환합니다.  `printf` 제품군별 quiet NaN의 표현에 대한 자세한 정보는 [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)을 참조하십시오.  
  
## 설명  
 `remainder` 함수는 `x`의 `r` \/ `y` 부동 소수점 나머지를 계산합니다. `x` \= `n` \* `y` \+ `r`이며, `n`이 `x` \/ `y`의 가장 가까운 정수 값인 반면 &#124;`n`일 때마다 `n` 은 짝수입니다. \- `x` \/ `y` &#124; \= 1\/2.  `r` \= 0이면, `r`은 `x`와 같은 부호를 가집니다.  
  
 C\+\+가 오버로딩을 허용하기 때문에 `float` 또는 `long double` 값을 사용하고 반환하는 `remainder`의 오버로드를 호출할 수 있습니다.  C 프로그램에서 `remainder`는 항상 2개의 double을 사용하고 하나의 double을 반환합니다.  
  
## 요구 사항  
  
|Function|필수 헤더|  
|--------------|-----------|  
|`remainder`, `remainderf`, `remainderl`|\<math.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```c  
// crt_remainder.c  
// This program displays a floating-point remainder.  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double w = -10.0, x = 3.0, z;  
  
   z = remainder(w, x);  
   printf("The remainder of %.2f / %.2f is %f\n", w, x, z);  
}  
```  
  
  **\-10.00 \/ 3.00의 나머지는 \-1.000000입니다.**   
## 해당 .NET Framework 항목  
 [System::Math::IEEERemainder](https://msdn.microsoft.com/en-us/library/system.math.ieeeremainder.aspx)  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [ldiv, lldiv](../../c-runtime-library/reference/ldiv-lldiv.md)   
 [imaxdiv](../../c-runtime-library/reference/imaxdiv.md)   
 [fmod, fmodf](../../c-runtime-library/reference/fmod-fmodf.md)   
 [remquo, remquof, remquol](../../c-runtime-library/reference/remquo-remquof-remquol.md)