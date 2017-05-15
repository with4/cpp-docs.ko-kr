---
title: "difftime, _difftime32, _difftime64 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _difftime32
- difftime
- _difftime64
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
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _difftime64
- difftime
- difftime64
- _difftime32
- difftime32
dev_langs:
- C++
helpviewer_keywords:
- _difftime32 function
- difftime function
- time, finding the difference
- difftime64 function
- _difftime64 function
- difftime32 function
ms.assetid: 4cc0ac2b-fc7b-42c0-8283-8c9d10c566d0
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: f6ab058a86a5635aa341c964644a291f61ba170b
ms.contentlocale: ko-kr
ms.lasthandoff: 03/30/2017

---
# <a name="difftime-difftime32-difftime64"></a>difftime, _difftime32, _difftime64
두 시간의 차이를 찾습니다.  
  
## <a name="syntax"></a>구문  
  
```  
double difftime(   
   time_t timer1,  
   time_t timer0   
);  
double _difftime32(   
   __time32_t timer1,  
   __time32_t timer0   
);  
double _difftime64(   
   __time64_t timer1,  
   __time64_t timer0   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `timer1`  
 종료 시간입니다.  
  
 `timer0`  
 시작 시간입니다.  
  
## <a name="return-value"></a>반환 값  
 `difftime`은 `timer0`에서 `timer1`까지의 경과된 시간(초)을 반환합니다. 반환되는 값은 배정밀도 부동 소수점 숫자입니다. 반환 값은 오류를 나타내는 0일 수 있습니다.  
  
## <a name="remarks"></a>설명  
 `difftime` 함수는 제공된 두 시간 값인 `timer0`과 `timer1` 사이의 차이를 계산합니다.  
  
 제공된 시간 값은 `time_t`의 범위 내에 있어야 합니다. `time_t`는 64비트 값입니다. 따라서 범위의 끝은 2038년 1월 18일 23:59:59(UTC)에서 3000년 12월 31일 23:59:59로 확장되었습니다. `time_t`의 낮은 범위는 계속 1970년 1월 1일 자정입니다.  
  
 `difftime`은 `_difftime32`가 정의되었는지의 여부에 따라 `_difftime64` 또는 `_USE_32BIT_TIME_T`로 계산되는 인라인 함수입니다. _difftime32 및 _difftime64는 시간 형식의 특정 크기를 강제로 사용하도록 직접 사용될 수 있습니다.  
  
 이러한 함수는 해당 함수 매개 변수의 유효성을 검사합니다. 매개 변수가 0 또는 음수인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용된 경우 이러한 함수가 0을 반환하고 `errno`를 `EINVAL`로 설정합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`difftime`|\<time.h>|  
|`_difftime32`|\<time.h>|  
|`_difftime64`|\<time.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```cpp  
// crt_difftime.c  
// This program calculates the amount of time  
// needed to do a floating-point multiply 100 million times.  
//  
  
#include <stdio.h>  
#include <stdlib.h>  
#include <time.h>  
#include <float.h>  
  
double RangedRand( float range_min, float range_max)  
{  
   // Generate random numbers in the half-closed interval  
   // [range_min, range_max). In other words,  
   // range_min <= random number < range_max  
   return ((double)rand() / (RAND_MAX + 1) * (range_max - range_min)  
            + range_min);  
}  
  
int main( void )  
{  
   time_t   start, finish;  
   long     loop;  
   double   result, elapsed_time;  
   double   arNums[3];  
  
   // Seed the random-number generator with the current time so that  
   // the numbers will be different every time we run.  
   srand( (unsigned)time( NULL ) );  
  
   arNums[0] = RangedRand(1, FLT_MAX);  
   arNums[1] = RangedRand(1, FLT_MAX);  
   arNums[2] = RangedRand(1, FLT_MAX);  
   printf( "Using floating point numbers %.5e %.5e %.5e\n", arNums[0], arNums[1], arNums[2] );  
  
   printf( "Multiplying 2 numbers 100 million times...\n" );  
  
   time( &start );  
   for( loop = 0; loop < 100000000; loop++ )  
      result = arNums[loop%3] * arNums[(loop+1)%3];   
   time( &finish );  
  
   elapsed_time = difftime( finish, start );  
   printf( "\nProgram takes %6.0f seconds.\n", elapsed_time );  
}  
  
```  
  
```Output  
Using random floating point numbers 1.04749e+038 2.01482e+038 1.72737e+038Multiplying 2 floating point numbers 100 million times...Program takes      3 seconds.Multiplying 2 floating point numbers 500 million times...  
  
Program takes      5 seconds.  
```  
  
## <a name="see-also"></a>참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [시간 관리](../../c-runtime-library/time-management.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)
