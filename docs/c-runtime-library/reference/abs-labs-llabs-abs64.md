---
title: "abs, labs, llabs _abs64 | Microsoft Docs"
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
  - "abs"
  - "_abs64"
  - "labs"
  - "llabs"
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
  - "stdlib/_abs64"
  - "math/abs"
  - "_abs64"
  - "abs"
  - "labs"
  - "math/labs"
  - "llabs"
  - "math/llabs"
  - "cmath/abs"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "절대 값"
  - "abs 함수"
  - "abs64 함수"
  - "_abs64 함수"
  - "절대값 계산"
ms.assetid: 60f789d1-4a1e-49f5-9e4e-0bdb277ea26a
caps.latest.revision: 29
caps.handback.revision: 29
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# abs, labs, llabs _abs64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

인수의 절대값을 계산 합니다.  
  
## 구문  
  
```  
int abs(   
   int n   
);  
long abs(   
   long n   
);   // C++ only  
long long abs(   
   long long n   
);   // C++ only  
double abs(   
   double n   
);   // C++ only  
long double abs(  
   long double n  
);   // C++ only  
float abs(  
   float n   
);   // C++ only  
long labs(  
   long n   
);  
long long llabs(  
   long long n   
);  
__int64 _abs64(   
   __int64 n   
);  
```  
  
#### 매개 변수  
 `n`  
 숫자 값입니다.  
  
## 반환 값  
 `abs`, `labs`, `llabs` 및 `_abs64` 매개 변수의 절대 값을 반환 하는 함수 `n`합니다. 반환되는 오류가 없습니다.  
  
## 설명  
 C \+ \+에서는 오버 로드를 허용 하므로의 오버 로드를 호출할 수 있습니다 `abs` 및 반환 하 `long`, `long long`, `float`, `double`, 및 `long double` 값입니다. 이러한 오버 로드는 \< cmath \> 헤더에 정의 됩니다. C 프로그램에서 `abs` 항상 사용 하 고 int를 반환 합니다.  
  
 **Microsoft 전용**  
  
 음수 정수 계열 형식일을 사용 하 여 나타낼 수 있는 범위가 해당 형식을 사용 하 여 나타낼 수 있는 양의 정수 범위 보다 큰 되므로 변환할 수 없는 이러한 함수에 인수를 제공할 수 있습니다. 인수의 절대값을 반환 형식으로 표현할 수 없는 경우는 `abs` 함수 인수 값을 변경 하지 않고 반환 합니다. 특히, `abs(INT_MIN)` 반환 `INT_MIN`, `labs(LONG_MIN)` 반환 `LONG_MIN`, `llabs(LLONG_MIN)` 반환 `LLONG_MIN`, 및 `_abs64(_I64_MIN)` 반환 `_I64_MIN`합니다. 즉,는 `abs` 함수는 양수 값을 보장 하기 위해 사용할 수 없습니다.  
  
 **Microsoft 전용 종료**  
  
## 요구 사항  
  
|루틴|필수 C 헤더|필수 c \+ \+ 헤더|  
|--------|-------------|-------------------|  
|`abs`, `labs`, `llabs`|\< h. h \> 또는 \< stdlib.h \>|\< cmath \>, \< d l i b \> \< stdlib.h \> 또는 \< h. h \>|  
|`_abs64`|\<stdlib.h\>|\< d l i b \> 또는 \< stdlib.h \>|  
  
 오버 로드 된 버전을 사용 하 여 `abs` c \+ \+에서는 \< cmath \> 헤더를 포함 해야 합니다.  
  
## 예제  
 이 프로그램을 계산 하 고 여러 가지 숫자의 절대 값을 표시 합니다.  
  
```c  
// crt_abs.c  
// Build: cl /W3 /TC crt_abs.c  
// This program demonstrates the use of the abs function  
// by computing and displaying the absolute values of  
// several numbers.  
  
#include <stdio.h>  
#include <math.h>  
#include <stdlib.h>  
#include <limits.h>  
  
int main( void )  
{  
    int ix = -4;  
    long lx = -41567L;  
    long long llx = -9876543210LL;  
    __int64 wx = -1;  
  
    // absolute 32 bit integer value  
    printf_s("The absolute value of %d is %d\n", ix, abs(ix));  
  
    // absolute long integer value  
    printf_s("The absolute value of %ld is %ld\n", lx, labs(lx));  
  
    // absolute long long integer value  
    printf_s("The absolute value of %lld is %lld\n", llx, llabs(llx));  
  
    // absolute 64 bit integer value  
    printf_s("The absolute value of 0x%.16I64x is 0x%.16I64x\n", wx,   
        _abs64(wx));  
  
    // Integer error cases:  
    printf_s("Microsoft implementation-specific results:\n");  
    printf_s(" abs(INT_MIN) returns %d\n", abs(INT_MIN));  
    printf_s(" labs(LONG_MIN) returns %ld\n", labs(LONG_MIN));  
    printf_s(" llabs(LLONG_MIN) returns %lld\n", llabs(LLONG_MIN));  
    printf_s(" _abs64(_I64_MIN) returns 0x%.16I64x\n", _abs64(_I64_MIN));  
}  
```  
  
```Output  
-4의 절대 값은 4-41567의 절대 값은-9876543210의 절대 값은 0xffffffffffffffff의 절대값은 9876543210 41567 0x0000000000000001 Microsoft 구현의 결과: abs(INT_MIN) 반환-2147483648 labs(LONG_MIN) 반환-2147483648 llabs(LLONG_MIN) 반환-9223372036854775808 _abs64(_I64_MIN) 반환 0x8000000000000000  
  
```  
  
## 해당 .NET Framework 항목  
 [System::Math::Abs](https://msdn.microsoft.com/en-us/library/system.math.abs.aspx)  
  
## 참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [\_cabs](../../c-runtime-library/reference/cabs.md)   
 [fabs, fabsf, fabsl](../../c-runtime-library/reference/fabs-fabsf-fabsl.md)   
 [imaxabs](../../c-runtime-library/reference/imaxabs.md)