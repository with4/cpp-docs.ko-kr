---
title: "remquo, remquof, remquol | Microsoft Docs"
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
  - "remquof"
  - "remquo"
  - "remquol"
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
  - "remquof"
  - "remquol"
  - "remquo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "remquol 함수"
  - "remquof 함수"
  - "remquo 함수"
ms.assetid: a1d3cb8b-8027-4cd3-8deb-04eb17f299fc
caps.latest.revision: 8
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# remquo, remquof, remquol
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

두 정수 값의 나머지를 계산하고 매개 변수에 지정된 위치에 부호 및 대략적인 지수의 크기와 함께 정수 값을 저장합니다.  
  
## 구문  
  
```  
double remquo(   
   double numer,  
   double denom,  
   int* quo  
);  
float remquo(   
   float numer,  
   float denom,  
   int* quo  
); /* C++ only */  
long double remquo(   
   long double numer,  
   long double denom,  
   int* quo  
); /* C++ only */  
float remquof(   
   float numer,  
   float denom,  
   int* quo  
);  
long double remquol(   
   long double numer,  
   long double denom,  
   int* quo  
);  
  
```  
  
#### 매개 변수  
 `numer`  
 분자입니다.  
  
 `denom`  
 분모입니다.  
  
 `quo`  
 기호 및 몫의 대략적인 크기 값을 저장하는 정수에 대한 포인터입니다.  
  
## 반환 값  
 `remquo`은 `x` \/ `y`의 부동 소수점 나머지를 반환합니다.  `y`의 값이 0.0인 경우 `remquo`이 quiet NaN을 반환합니다.  `printf` 제품군별 quiet NaN의 표현에 대한 자세한 정보는 [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)을 참조하십시오.  
  
## 설명  
 `remquo` 함수는 `x` \= `i` `*` `y` \+ `f`로 수행되는 `x` \/ `y`의 부동 소수점 나머지 `f`를 계산합니다. 여기서 `i`는 정수이고 `f`에는 `x`와 같은 기호가 있으며 `f`의 절대값은 `y`의 절대값보다 작습니다.  
  
 C\+\+는 오버로드를 허용하기 때문에 `float` 또는 `long double` 값을 사용하고 반환하는 `remquo`의 오버로드를 호출할 수 있습니다.  C 프로그램에서 `remquo`는 항상 2개의 double을 사용하고 하나의 double을 반환합니다.  
  
## 요구 사항  
  
|Function|필수 헤더|  
|--------------|-----------|  
|`remquo`, `remquof`, `remquol`|\<math.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```c  
// crt_remquo.c  
// This program displays a floating-point remainder.  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double w = -10.0, x = 3.0, z;  
   int quo = 0;  
  
   z = remquo(w, x, &quo);  
   printf("The remainder of %.2f / %.2f is %f\n", w, x, z);  
   printf("Approximate signed quotient is %d\n", quo);  
}  
```  
  
  **\-10.00 \/ 3.00의 나머지는 \-1.000000입니다.**  
**대략적인 부호가 있는 몫은 \-3입니다.**   
## 해당 .NET Framework 항목  
 [System::Math::IEEERemainder](https://msdn.microsoft.com/en-us/library/system.math.ieeeremainder.aspx)  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [ldiv, lldiv](../../c-runtime-library/reference/ldiv-lldiv.md)   
 [imaxdiv](../../c-runtime-library/reference/imaxdiv.md)   
 [fmod, fmodf](../../c-runtime-library/reference/fmod-fmodf.md)   
 [remainder, remainderf, remainderl](../../c-runtime-library/reference/remainder-remainderf-remainderl.md)