---
title: "gmtime, _gmtime32, _gmtime64 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _gmtime32
- gmtime
- _gmtime64
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
- gmtime
- _gmtime32
- _gmtime64
dev_langs:
- C++
helpviewer_keywords:
- gmtime32 function
- _gmtime64 function
- gmtime function
- time functions
- _gmtime32 function
- gmtime64 function
- time structure conversion
ms.assetid: 315501f3-477e-475d-a414-ef100ee0db27
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4646902145796ede0659493cb0805cfdf85bb52e
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="gmtime-gmtime32-gmtime64"></a>gmtime, _gmtime32, _gmtime64
시간 값을 구조체로 변환합니다. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [gmtime_s, _gmtime32_s, _gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
struct tm *gmtime(   
   const time_t *timer   
);  
struct tm *_gmtime32(   
   const __time32_t *timer   
);  
struct tm *_gmtime64(   
   const __time64_t *timer   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `timer`  
 저장된 시간에 대한 포인터입니다. 시간은 1970년 1월 1일 자정(00:00:00)(UTC(협정 세계시)) 이후 경과한 시간(초)으로 표현됩니다.  
  
## <a name="return-value"></a>반환 값  
 [tm](../../c-runtime-library/standard-types.md) 형식의 구조체에 대한 포인터입니다. 반환된 구조체의 필드에는 현지 시간이 아닌 UTC로 계산된 `timer` 인수 값이 포함됩니다. 각 구조체 필드는 다음과 같이 `int` 형식입니다.  
  
 `tm_sec`  
 초 후 1 분 (0-59).  
  
 `tm_min`  
 분 후에 시간 (0-59).  
  
 `tm_hour`  
 자정 이후의 시간 (0-23).  
  
 `tm_mday`  
 날짜 (1-31)입니다.  
  
 `tm_mon`  
 월 (0-11; 1 월 = 0).  
  
 `tm_year`  
 연도(현재 연도 - 1900).  
  
 `tm_wday`  
 요일 (0-6; 일요일 = 0).  
  
 `tm_yday`  
 연간 일자 (0-365; 1 월 1 일 = 0).  
  
 `tm_isdst`  
 `gmtime`의 경우 항상 0입니다.  
  
 `gmtime`, `mktime`, `mkgmtime` 및 `localtime`의 32비트 및 64비트 버전은 모두 변환을 위해 스레드당 하나의 공통 `tm` 구조체를 사용합니다. 이러한 함수 중 하나를 호출할 때마다 이전 호출의 결과가 삭제됩니다. `timer`가 1970년 1월 1일 자정(UTC) 이전의 날짜를 나타내면 `gmtime`은 `NULL`을 반환합니다. 반환되는 오류가 없습니다.  
  
 `__time64_t` 구조체를 사용하는 `_gmtime64`는 3000년 12월 31일 23:59:59(UTC)까지 날짜를 표현할 수 있습니다. 반면, `_gmtime32`는 2038년 1월 18일 23:59:59(UTC)까지의 날짜만 나타냅니다. 1970년 1월 1일 자정은 두 함수 모두에 대한 날짜 범위의 하한입니다.  
  
 `gmtime`은 `_gmtime64`로 계산되는 인라인 함수이며 `time_t`는 `_USE_32BIT_TIME_T`가 정의되지 않은 경우 `__time64_t`와 동일합니다. 컴파일러에서 `time_t`를 이전 32비트 `time_t`로 해석하게 해야 하는 경우 `_USE_32BIT_TIME_T`를 정의할 수 있지만, 이렇게 하면 `gmtime`이 `_gmtime32`에 인라인되고 `time_t`가 `__time32_t`로 정의됩니다. 이 방법은 64비트 플랫폼에서 허용되지 않고 2038년 1월 18일 이후 응용 프로그램이 작동하지 않을 수 있기 때문에 권장되지 않습니다.  
  
 이러한 함수는 해당 함수 매개 변수의 유효성을 검사합니다. `timer`가 null 포인터이거나 timer 값이 음수인 경우 이러한 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 계속해서 실행하도록 허용된 경우 이 함수는 `NULL`을 반환하며 `errno`를 `EINVAL`로 설정합니다.  
  
## <a name="remarks"></a>설명  
 `_gmtime32` 함수는 `timer` 값을 분할하고 TIME.H에 정의된 `tm` 형식의 정적으로 할당된 구조체에 저장합니다. `timer` 값은 대개 `time` 함수 호출에서 가져옵니다.  
  
> [!NOTE]
>  대부분의 경우 대상 환경에서는 일광 절약 시간이 적용되는지 확인하려고 합니다. C 런타임 라이브러리에서는 DST(일광 절약 시간) 계산 구현을 위한 미국 규칙이 사용된다고 가정합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`gmtime`|\<time.h>|  
|`_gmtime32`|\<time.h>|  
|`_gmtime64`|\<time.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예  
  
```C  
// crt_gmtime.c  
// compile with: /W3  
// This program uses _gmtime64 to convert a long-  
// integer representation of coordinated universal time  
// to a structure named newtime, then uses asctime to  
// convert this structure to an output string.  
  
#include <time.h>  
#include <stdio.h>  
  
int main( void )  
{  
   struct tm *newtime;  
   __int64 ltime;  
   char buff[80];  
  
   _time64( &ltime );  
  
   // Obtain coordinated universal time:  
   newtime = _gmtime64( &ltime ); // C4996  
   // Note: _gmtime64 is deprecated; consider using _gmtime64_s  
   asctime_s( buff, sizeof(buff), newtime );  
   printf( "Coordinated universal time is %s\n", buff );  
}  
```  
  
```Output  
Coordinated universal time is Tue Feb 12 23:11:31 2002  
```  
  
## <a name="see-also"></a>참고 항목  
 [시간 관리](../../c-runtime-library/time-management.md)   
 [asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime_s, _gmtime32_s, _gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [_mkgmtime, _mkgmtime32, _mkgmtime64](../../c-runtime-library/reference/mkgmtime-mkgmtime32-mkgmtime64.md)   
 [mktime, _mktime32, _mktime64](../../c-runtime-library/reference/mktime-mktime32-mktime64.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)