---
title: "div | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "div"
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
  - "api-ms-win-crt-utility-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "div"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "div 함수"
  - "정수 나누기"
  - "몫"
  - "몫, 계산"
  - "나머지 계산"
ms.assetid: 8ae80d97-54fd-499e-b14c-e30993b58119
caps.latest.revision: 15
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# div
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

몫과 나머지 두 정수 값을 계산합니다.  
  
## 구문  
  
```  
div_t div(   
   int numer,  
   int denom   
);  
ldiv_t div(  
   long numer,  
   long denom  
); /* C++ only */   
lldiv_t div(  
   long long numer,  
   long long denom  
); /* C++ only */  
```  
  
#### 매개 변수  
 `numer`  
 분자입니다.  
  
 `denom`  
 분모입니다.  
  
## 반환 값  
 이 `int` 형식의 인수로 사용되어져 호출된 `div` 은, 몫과 나머지를 구성하는 `div_t` 형식의 구조체를 반환합니다.  이 `long` 형식의 인수를 사용한 반환값은 `ldiv_t`입니다.  둘 다 `div_t` 및 `ldiv_t` STDLIB.H.에 정의됩니다.  
  
## 설명  
 `div` 함수는 `numer`를 `denom`으로 나누어 몫과 나머지를 계산합니다.  이 [div\_t](../../c-runtime-library/standard-types.md) 구조체에는 몫 `int` `quot`과 나머지 `int` `rem`이 포함됩니다.  지수의 기호는 수학적 지수의 기호와 동일합니다.  절대 값은 수학적 몫의 절대 값 보다 작은 가장 큰 정수입니다.  분모가 0 이면 프로그램은 오류 메시지와 함께 프로그램이 종료됩니다.  
  
 이 `long` 또는 `long long` 형식의 인수를 받는 오버로드는 오직 c\+\+ 코드를 사용할 수 있습니다.  이 [ldiv\_t](../../c-runtime-library/standard-types.md) 반환 형식은 `long` `quot` 과 `long` `rem` 구성원을 포함하고, [lldiv\_t](../../c-runtime-library/standard-types.md) 반환 형식은 `div_t` 구성원과 동일한 의미를 가지는 `long long quot` 와 `long long rem` 을 포합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`div`|\<stdlib.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```  
// crt_div.c  
// arguments: 876 13  
  
// This example takes two integers as command-line  
// arguments and displays the results of the integer  
// division. This program accepts two arguments on the  
// command line following the program name, then calls  
// div to divide the first argument by the second.  
// Finally, it prints the structure members quot and rem.  
//  
  
#include <stdlib.h>  
#include <stdio.h>  
#include <math.h>  
  
int main( int argc, char *argv[] )  
{  
   int x,y;  
   div_t div_result;  
  
   x = atoi( argv[1] );  
   y = atoi( argv[2] );  
  
   printf( "x is %d, y is %d\n", x, y );  
   div_result = div( x, y );  
   printf( "The quotient is %d, and the remainder is %d\n",  
           div_result.quot, div_result.rem );  
}  
```  
  
  **x는 876, y가 13**  
**몫은 67, 이며 나머지 5**   
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)을 참조하십시오.  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [ldiv, lldiv](../../c-runtime-library/reference/ldiv-lldiv.md)   
 [imaxdiv](../../c-runtime-library/reference/imaxdiv.md)