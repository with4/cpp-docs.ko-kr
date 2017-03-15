---
title: "difftime, _difftime32, _difftime64 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_difftime32"
  - "difftime"
  - "_difftime64"
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
  - "api-ms-win-crt-time-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_difftime64"
  - "difftime"
  - "difftime64"
  - "_difftime32"
  - "difftime32"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_difftime32 함수"
  - "difftime 함수"
  - "시간, 차이점 찾기"
  - "difftime64 함수"
  - "_difftime64 함수"
  - "difftime32 함수"
ms.assetid: 4cc0ac2b-fc7b-42c0-8283-8c9d10c566d0
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# difftime, _difftime32, _difftime64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

두 시간의 차이를 찾습니다.  
  
## 구문  
  
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
  
#### 매개 변수  
 `timer1`  
 종료 시간입니다.  
  
 `timer0`  
 시작 시간입니다.  
  
## 반환 값  
 `difftime`은 `timer0`에서 `timer1`까지의 경과된 시간\(초\)을 반환합니다. 반환되는 값은 배정밀도 부동 소수점 숫자입니다. 반환 값은 오류를 나타내는 0일 수 있습니다.  
  
## 설명  
 `difftime` 함수는 제공된 두 시간 값인 `timer0`과 `timer1` 사이의 차이를 계산합니다.  
  
 제공된 시간 값은 `time_t`의 범위 내에 있어야 합니다.`time_t`는 64비트 값입니다. 따라서 범위의 끝에서에서 확장 되었습니다 23시 59분: 59 2038 년 1 월 18 일 UTC 23시 59분: 59으로 3000 년 12 월 31 일입니다.`time_t`의 낮은 범위는 계속 1970년 1월 1일 자정입니다.  
  
 `difftime`은 `_difftime32`가 정의되었는지의 여부에 따라 `_difftime64` 또는 `_USE_32BIT_TIME_T`로 계산되는 인라인 함수입니다. \_difftime32 및 \_difftime64는 시간 형식의 특정 크기를 강제로 사용하도록 직접 사용될 수 있습니다.  
  
 이러한 함수는 해당 함수 매개 변수의 유효성을 검사합니다. 경우 매개 변수는 0 또는 음수는 잘못 된 매개 변수 처리기가 호출에 설명 된 대로 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 이러한 함수를 계속 실행 허용 되는 경우 0을 반환 하 고 설정 `errno` 를 `EINVAL`합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`difftime`|\<time.h\>|  
|`_difftime32`|\<time.h\>|  
|`_difftime64`|\<time.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
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
1.04749e + 038 2.01482e + 038 1.72737e + 038Multiplying 숫자 임의의 부동 소수점을 사용 하 여 2 부동 소수점 숫자 100 백만 번... 프로그램에는 3 초 걸립니다. 부동 곱하는 2를 가리키고 숫자 500 백만 번... Program takes      5 seconds.  
```  
  
## 해당 .NET Framework 항목  
 [System::DateTime::Subtract](https://msdn.microsoft.com/en-us/library/system.datetime.subtract.aspx)  
  
## 참고 항목  
 [부동 소수점 지원](../../c-runtime-library/floating-point-support.md)   
 [시간 관리](../../c-runtime-library/time-management.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)