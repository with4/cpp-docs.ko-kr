---
title: "gmtime_s, _gmtime32_s, _gmtime64_s | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _gmtime32_s
- gmtime_s
- _gmtime64_s
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
- _gmtime_s
- gmtime64_s
- gmtime32_s
- _gmtime64_s
- gmtime_s
- _gmtime32_s
dev_langs:
- C++
helpviewer_keywords:
- gmtime_s function
- gmtime32_s function
- time functions
- gmtime64_s function
- _gmtime64_s function
- time structure conversion
- _gmtime_s function
- _gmtime32_s function
ms.assetid: 261c7df0-2b0c-44ba-ba61-cb83efaec60f
caps.latest.revision: 29
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: e130b125651c29a4ba2607b47b02b95c81468869
ms.contentlocale: ko-kr
ms.lasthandoff: 04/01/2017

---
# <a name="gmtimes-gmtime32s-gmtime64s"></a>gmtime_s, _gmtime32_s, _gmtime64_s
시간 값을 구조체로 변환합니다. 이러한 함수는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 있는 [_gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)의 버전입니다.  
  
## <a name="syntax"></a>구문  
  
```  
errno_t gmtime_s(  
   struct tm* _tm,  
   const __time_t* time  
);  
errno_t _gmtime32_s(  
   struct tm* _tm,  
   const __time32_t* time  
);  
errno_t _gmtime64_s(  
   struct tm* _tm,  
   const __time64_t* time   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `_tm`  
 `tm` 구조체에 대한 포인터입니다. 반환된 구조체의 필드에는 현지 시간이 아닌 UTC로 계산된 `timer` 인수 값이 포함됩니다.  
  
 `time`  
 저장된 시간에 대한 포인터입니다. 시간은 1970년 1월 1일 자정(00:00:00)(UTC(협정 세계시)) 이후 경과한 시간(초)으로 표현됩니다.  
  
## <a name="return-value"></a>반환 값  
 성공할 경우 0입니다. 오류가 있을 경우 반환 값은 오류 코드입니다. 오류 코드는 Errno.h에 정의됩니다. 이러한 오류의 목록을 보려면 [errno](../../c-runtime-library/errno-constants.md)를 참조하세요.  
  
### <a name="error-conditions"></a>오류 조건  
  
|`_tm`|`time`|반환|`_tm`의 값|  
|-----------|------------|------------|--------------------|  
|`NULL`|모두|`EINVAL`|수정되지 않습니다.|  
|`NULL` 아님(유효한 메모리를 가리킴)|`NULL`|`EINVAL`|모든 필드가 -1로 설정됩니다.|  
|`NULL` 아님|< 0|`EINVAL`|모든 필드가 -1로 설정됩니다.|  
  
 처음 두 오류 조건의 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수가 호출됩니다. 계속해서 실행하도록 허용된 경우 이러한 함수는 `errno`를 `EINVAL`로 설정하고 `EINVAL`을 반환합니다.  
  
## <a name="remarks"></a>설명  
 `_gmtime32_s` 함수는 `time` 값을 분할하고 Time.h에 정의된 `tm` 형식의 구조체에 저장합니다. 구조체 주소는 `_tm`에 전달됩니다. `time` 값은 대개 `time` 함수 호출에서 가져옵니다.  
  
> [!NOTE]
>  대상 환경에서는 일광 절약 시간이 적용되는지 확인해야 합니다. C 런타임 라이브러리에서는 일광 절약 시간 계산 구현을 위한 미국의 규칙이 사용된다고 가정합니다.  
  
 각 구조체 필드는 다음 표에 나와 있는 대로 `int` 형식입니다.  
  
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
  
 `__time64_t` 구조체를 사용하는 `_gmtime64_s`는 3000년 12월 31일 23:59:59(UTC)까지 날짜를 표현할 수 있습니다. 반면, `gmtime32_s`는 2038년 1월 18일 23:59:59(UTC)까지의 날짜만 나타냅니다. 1970년 1월 1일 자정은 이러한 두 함수 모두에 대한 날짜 범위의 하한입니다.  
  
 `gmtime_s`는 `_gmtime64_s`로 계산되는 인라인 함수이며 `time_t`는 `__time64_t`와 동일합니다. 컴파일러에서 `time_t`를 이전의 32비트 `time_t`로 해석하게 해야 하는 경우 `_USE_32BIT_TIME_T`를 정의할 수 있습니다. 이렇게 하면 `gmtime_s`가 `_gmtime32_s`에 인라인됩니다. 2038년 1월 18일 이후에는 응용 프로그램에서 오류가 발생할 수 있으므로 이 방식은 사용하지 않는 것이 좋으며, 64비트 플랫폼에서는 이러한 방식이 허용되지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`gmtime_s`|\<time.h>|  
|`_gmtime32_s`|\<time.h>|  
|`_gmtime64_s`|\<time.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```  
// crt_gmtime64_s.c  
// This program uses _gmtime64_s to convert a 64-bit  
// integer representation of coordinated universal time  
// to a structure named newtime, then uses asctime_s to  
// convert this structure to an output string.  
  
#include <time.h>  
#include <stdio.h>  
  
int main( void )  
{  
   struct tm newtime;  
   __int64 ltime;  
   char buf[26];  
   errno_t err;  
  
   _time64( &ltime );  
  
   // Obtain coordinated universal time:   
   err = _gmtime64_s( &newtime, &ltime );  
   if (err)  
   {  
      printf("Invalid Argument to _gmtime64_s.");  
   }  
  
   // Convert to an ASCII representation   
   err = asctime_s(buf, 26, &newtime);  
   if (err)  
   {  
      printf("Invalid Argument to asctime_s.");  
   }  
  
   printf( "Coordinated universal time is %s\n",   
           buf );  
}  
```  
  
```Output  
Coordinated universal time is Fri Apr 25 20:12:33 2003  
```  
  
## <a name="see-also"></a>참고 항목  
 [시간 관리](../../c-runtime-library/time-management.md)   
 [asctime_s, _wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime_s, _localtime32_s, _localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [_mkgmtime, _mkgmtime32, _mkgmtime64](../../c-runtime-library/reference/mkgmtime-mkgmtime32-mkgmtime64.md)   
 [mktime, _mktime32, _mktime64](../../c-runtime-library/reference/mktime-mktime32-mktime64.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)
