---
title: "ldiv, lldiv | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "ldiv"
  - "lldiv"
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
  - "ldiv"
  - "lldiv"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "몫 계산"
  - "나머지 계산"
  - "ldiv 함수"
  - "lldiv 함수"
  - "몫, 계산"
  - "나머지 계산"
ms.assetid: 68ab5d83-27a4-479c-9d52-d055eb139eca
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# ldiv, lldiv
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

한 번의 작업으로 몫과 나머지 두 개의 정수를 계산합니다.  
  
## 구문  
  
```  
ldiv_t ldiv(  
   long numer,  
   long denom   
);  
lldiv_t lldiv(  
   long long numer,  
   long long denom   
);  
```  
  
#### 매개 변수  
 `numer`  
 열거자  
  
 `denom`  
 분모입니다.  
  
## 반환 값  
 `ldiv` 은 형식의 구조 [ldiv\_t](../../c-runtime-library/standard-types.md) 를 반환합니다. 이것은 몫과 나머지를 구성 합니다.  `lldiv` 은 형식의 구조 [ldiv\_t](../../c-runtime-library/standard-types.md) 를 반환합니다. 이것은 몫과 나머지를 구성 합니다.  
  
## 설명  
 `ldiv` 와 `lldiv` 함수는 `numer` 를 `denom`에 의해서 나눕니다. 그리고 몫과 나머지를 계산합니다.  지수의 기호는 수학적 지수의 기호와 동일합니다.  절대 값은 수학적 몫의 절대 값 보다 작은 가장 큰 정수입니다.  분모가 0 이면 프로그램은 오류 메시지와 함께 프로그램이 종료됩니다.  `ldiv` 및 `lldiv` 는 `div` 와 동일합니다. `ldiv` 인 인수를 제외합니다. 그리고 반환된 구조체의 멤버는 모든 종류의 `long` 이고, `lldiv` 형식의 반환 된 구조체의 멤버는 `long long`입니다.  
  
 `ldiv_t` 및 `lldiv_t` 구조체는 \<stdlib.h\>에 의해 정의됩니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`ldiv`, `lldiv`|\<stdlib.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 예제  
  
```  
// crt_ldiv.c  
  
#include <stdlib.h>  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   long x = 5149627, y = 234879;  
   ldiv_t div_result;  
  
   div_result = ldiv( x, y );  
   printf( "For %ld / %ld, the quotient is ", x, y );  
   printf( "%ld, and the remainder is %ld\n",   
            div_result.quot, div_result.rem );  
}  
```  
  
## Output  
  
```  
For 5149627 / 234879, the quotient is 21, and the remainder is 217168  
```  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)을 참조하십시오.  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [div](../../c-runtime-library/reference/div.md)   
 [imaxdiv](../../c-runtime-library/reference/imaxdiv.md)