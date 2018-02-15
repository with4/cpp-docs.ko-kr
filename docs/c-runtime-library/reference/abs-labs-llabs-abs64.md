---
title: "abs, labs, llabs, _abs64 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- abs
- _abs64
- labs
- llabs
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
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- stdlib/_abs64
- math/abs
- _abs64
- abs
- labs
- math/labs
- llabs
- math/llabs
- cmath/abs
dev_langs:
- C++
helpviewer_keywords:
- absolute values
- abs function
- abs64 function
- _abs64 function
- calculating absolute values
ms.assetid: 60f789d1-4a1e-49f5-9e4e-0bdb277ea26a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1dc1e7532c715a045c2b76c3be2ef915f82693a1
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="abs-labs-llabs-abs64"></a>abs, labs, llabs, _abs64
인수의 절대값을 계산합니다.  
  
## <a name="syntax"></a>구문  
  
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
  
#### <a name="parameters"></a>매개 변수  
 `n`  
 숫자 값입니다.  
  
## <a name="return-value"></a>반환 값  
 `abs`, `labs`, `llabs` 및 `_abs64` 함수는 `n` 매개 변수의 절대값을 반환합니다. 반환되는 오류가 없습니다.  
  
## <a name="remarks"></a>설명  
 C++에서는 오버로드를 허용하므로 `long`, `long long`, `float`, `double` 및 `long double` 값을 사용 및 반환하는 `abs`의 오버로드를 호출할 수 있습니다. 이러한 오버로드는 \<cmath> 헤더에 정의됩니다. C 프로그램에서 `abs`는 항상 정수를 사용 및 반환합니다.  
  
 **Microsoft 전용**  
  
 임의의 정수 형식을 사용하여 나타낼 수 있는 음의 정수 범위는 해당 형식을 사용하여 나타낼 수 있는 양의 정수 범위보다 크기 때문에 이러한 함수에 변환할 수 없는 인수를 제공할 수 있습니다. 인수의 절대값을 반환 형식으로 나타낼 수 없는 경우 `abs` 함수는 변경되지 않은 인수 값을 반환합니다. 특히 `abs(INT_MIN)`는 `INT_MIN`, `labs(LONG_MIN)`는 `LONG_MIN`, `llabs(LLONG_MIN)`는 `LLONG_MIN`, `_abs64(_I64_MIN)`는 `_I64_MIN`을 반환합니다. 즉, 양수 값을 보장하기 위해 `abs` 함수를 사용할 수 없습니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 C 헤더|필수 C++ 헤더|  
|-------------|-----------------------|---------------------------|  
|`abs`, `labs`, `llabs`|\<math.h> 또는 \<stdlib.h>|\<cmath>, \<cstdlib>, \<stdlib.h> 또는 \<math.h>|  
|`_abs64`|\<stdlib.h>|\<cstdlib> 또는 \<stdlib.h>|  
  
 C++에서 `abs`의 오버로드된 버전을 사용하려면 \<cmath> 헤더를 포함해야 합니다.  
  
## <a name="example"></a>예  
 이 프로그램은 여러 숫자의 절대 값을 계산하여 표시합니다.  
  
```C  
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
The absolute value of -4 is 4  
The absolute value of -41567 is 41567  
The absolute value of -9876543210 is 9876543210  
The absolute value of 0xffffffffffffffff is 0x0000000000000001  
Microsoft implementation-specific results:  
 abs(INT_MIN) returns -2147483648  
 labs(LONG_MIN) returns -2147483648  
 llabs(LLONG_MIN) returns -9223372036854775808  
 _abs64(_I64_MIN) returns 0x8000000000000000  
  
```  
  
## <a name="see-also"></a>참고 항목  
 [데이터 변환](../../c-runtime-library/data-conversion.md)   
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [_cabs](../../c-runtime-library/reference/cabs.md)   
 [fabs, fabsf, fabsl](../../c-runtime-library/reference/fabs-fabsf-fabsl.md)   
 [imaxabs](../../c-runtime-library/reference/imaxabs.md)
