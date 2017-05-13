---
title: "_ftime, _ftime32, _ftime64 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ftime64
- _ftime
- _ftime32
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
- _ftime32
- _ftime
- _ftime64
- ftime64
- ftime
- ftime32
dev_langs:
- C++
helpviewer_keywords:
- ftime64 function
- _ftime64 function
- current time
- _ftime function
- ftime function
- _ftime32 function
- ftime32 function
- time, getting current
ms.assetid: 96bc464c-3bcd-41d5-a212-8bbd836b814a
caps.latest.revision: 27
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: ed69cd73a42889e56dc258ce66e56db3210dfc95
ms.contentlocale: ko-kr
ms.lasthandoff: 04/04/2017

---
# <a name="ftime-ftime32-ftime64"></a>_ftime, _ftime32, _ftime64
현재 시간을 가져옵니다. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [_ftime_s, _ftime32_s, _ftime64_s](../../c-runtime-library/reference/ftime-s-ftime32-s-ftime64-s.md)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
void _ftime(   
   struct _timeb *timeptr   
);  
void _ftime32(   
   struct __timeb32 *timeptr   
);  
void _ftime64(   
   struct __timeb64 *timeptr   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `timeptr`  
 `_timeb`, `__timeb32` 또는 `__timeb64` 구조체에 대한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 `_ftime` 함수는 현재 현지 시간을 가져오고에서 가리키는 구조에 저장 `timeptr`합니다. `_timeb`, `__timeb32`, 및 `__timeb64` 구조 SYS\Timeb.h에 정의 됩니다. 구조체에는 다음 표에 나와 있는 4개 필드가 포함됩니다.  
  
 `dstflag`  
 현지 시간대에 현재 일광 절약 시간이 적용된 경우 0이 아닌 값. 일광 절약 시간을 결정하는 방법에 대한 자세한 내용은 [_tzset](../../c-runtime-library/reference/tzset.md)를 참조하세요.  
  
 `millitm`  
 1초 미만의 시간(밀리초)입니다.  
  
 `time`  
 1970년 1월 1일 자정(00:00:00)(UTC(협정 세계시)) 이후의 시간(초)입니다.  
  
 `timezone`  
 서쪽으로 이동할 경우 UTC와 현지 시간 사이의 차이(분)입니다. `timezone` 값은 전역 변수 `_timezone` 값에 따라 설정됩니다(`_tzset` 참조).  
  
 `__timeb64` 구조체를 사용하는 `_ftime64`는 3000년 12월 31일 23:59:59(UTC)까지 파일 생성 날짜를 표현할 수 있습니다. 반면, `_ftime32`는 2038년 1월 18일 23:59:59(UTC)까지의 날짜만 나타냅니다. 1970년 1월 1일 자정은 이러한 모든 함수에 대한 날짜 범위의 하한입니다.  
  
 `_ftime`은 `_ftime64`와 동일하며, `_timeb`는 64비트 시간을 포함합니다. `_USE_32BIT_TIME_T`가 정의되지 않는 한 그러하며, 이 경우 이전 동작이 적용됩니다. `_ftime`는 32비트 시간을 사용하고 `_timeb`는 32비트 시간을 포함합니다.  
  
 `_ftime`는 매개 변수의 유효성을 검사합니다. `timeptr`로 null 포인터를 전달한 경우 이 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)의 설명대로 잘못된 매개 변수 처리기를 호출합니다. 계속해서 실행하도록 허용된 경우 함수가`errno`를 `EINVAL`로 설정합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|함수|필수 헤더|  
|--------------|---------------------|  
|`_ftime`|\<sys/types.h> 및 \<sys/timeb.h>|  
|`_ftime32`|\<sys/types.h> 및 \<sys/timeb.h>|  
|`_ftime64`|\<sys/types.h> 및 \<sys/timeb.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```  
// crt_ftime.c  
// compile with: /W3  
// This program uses _ftime to obtain the current  
// time and then stores this time in timebuffer.  
  
#include <stdio.h>  
#include <sys/timeb.h>  
#include <time.h>  
  
int main( void )  
{  
   struct _timeb timebuffer;  
   char timeline[26];  
   errno_t err;  
   time_t time1;  
   unsigned short millitm1;  
   short timezone1;  
   short dstflag1;  
  
   _ftime( &timebuffer ); // C4996  
   // Note: _ftime is deprecated; consider using _ftime_s instead  
  
   time1 = timebuffer.time;  
   millitm1 = timebuffer.millitm;  
   timezone1 = timebuffer.timezone;  
   dstflag1 = timebuffer.dstflag;  
  
   printf( "Seconds since midnight, January 1, 1970 (UTC): %I64d\n",   
   time1);  
   printf( "Milliseconds: %d\n", millitm1);  
   printf( "Minutes between UTC and local time: %d\n", timezone1);  
   printf( "Daylight savings time flag (1 means Daylight time is in "  
           "effect): %d\n", dstflag1);   
  
   err = ctime_s( timeline, 26, & ( timebuffer.time ) );  
   if (err)  
   {  
       printf("Invalid argument to ctime_s. ");  
   }  
   printf( "The time is %.19s.%hu %s", timeline, timebuffer.millitm,  
           &timeline[20] );  
}  
```  
  
```Output  
Seconds since midnight, January 1, 1970 (UTC): 1051553334  
Milliseconds: 230  
Minutes between UTC and local time: 480  
Daylight savings time flag (1 means Daylight time is in effect): 1  
The time is Mon Apr 28 11:08:54.230 2003  
```  
  
## <a name="see-also"></a>참고 항목  
 [시간 관리](../../c-runtime-library/time-management.md)   
 [asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)
