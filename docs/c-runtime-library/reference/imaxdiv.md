---
title: "imaxdiv | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "imaxdiv"
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
  - "imaxdiv"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "imaxdiv 함수"
ms.assetid: 7d90126f-fdc2-4986-9cdf-94e4c9123d26
caps.latest.revision: 7
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# imaxdiv
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

단일 연산으로 모든 크기의 두 정수 값의 몫과 나머지를 계산합니다.  
  
## 구문  
  
```  
imaxdiv_t imaxdiv(   
   intmax_t numer,  
   intmax_t denom   
);   
```  
  
#### 매개 변수  
 `numer`  
 분자입니다.  
  
 `denom`  
 분모입니다.  
  
## 반환 값  
 형식 [intmax\_t](../../c-runtime-library/standard-types.md)의 인수를 사용하여 호출한 `imaxdiv`은 몫과 나머지를 구성하는 형식 [imaxdiv\_t](../../c-runtime-library/standard-types.md)의 구조체를 반환합니다.  
  
## 설명  
 `imaxdiv` 함수는 `numer`를 `denom`으로 나누어 몫과 나머지를 계산합니다.  `imaxdiv_t` 구조체에는 몫 `intmax_t``quot`과 나머지 `intmax_t``rem`가 포함됩니다.  지수의 기호는 수학적 지수의 기호와 동일합니다.  절대 값은 수학적 몫의 절대 값 보다 작은 가장 큰 정수입니다.  분모가 0 이면 프로그램은 오류 메시지와 함께 프로그램이 종료됩니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`imaxdiv`|\<inttypes.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```  
// crt_imaxdiv.c  
// Build using: cl /W3 /Tc crt_imaxdiv.c  
// This example takes two integers as command-line  
// arguments and calls imaxdiv to divide the first   
// argument by the second, then displays the results.  
  
#include <stdio.h>  
#include <stdlib.h>  
#include <inttypes.h>  
  
int main(int argc, char *argv[])  
{  
   intmax_t x,y;  
   imaxdiv_t div_result;  
  
   x = atoll(argv[1]);  
   y = atoll(argv[2]);  
  
   printf("The call to imaxdiv(%lld, %lld)\n", x, y);  
   div_result = imaxdiv(x, y);  
   printf("results in a quotient of %lld, and a remainder of %lld\n\n",  
          div_result.quot, div_result.rem);  
}  
```  
  
 `9460730470000000 8766` 명령줄 매개 변수를 만든 다음 호출한 경우 코드가 이 출력을 생성합니다.  
  
  **imaxdiv에 대한 호출\(9460730470000000, 8766\)**  
**1079252848505의 몫 및 5170의 나머지가 발생합니다.**   
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)을 참조하십시오.  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [div](../../c-runtime-library/reference/div.md)   
 [ldiv, lldiv](../../c-runtime-library/reference/ldiv-lldiv.md)