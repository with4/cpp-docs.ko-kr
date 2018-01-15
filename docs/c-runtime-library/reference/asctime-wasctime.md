---
title: "asctime, _wasctime | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wasctime
- asctime
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
- _tasctime
- asctime
- _wasctime
dev_langs: C++
helpviewer_keywords:
- asctime function
- tasctime function
- wasctime function
- _tasctime function
- _wasctime function
- time structure conversion
- time, converting
ms.assetid: 974f1727-10ff-4ed4-8cac-2eb2d681f576
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 377b785b2803dc7cce09e55baeb31323bf83b4b6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="asctime-wasctime"></a>asctime, _wasctime
`tm` 시간 구조체를 문자열로 변환합니다. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [asctime_s, _wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
char *asctime(   
   const struct tm *timeptr   
);  
wchar_t *_wasctime(   
   const struct tm *timeptr   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `timeptr`  
 시간/날짜 구조체입니다.  
  
## <a name="return-value"></a>반환 값  
 `asctime`은 포인터를 문자열 결과로 반환하고, `_wasctime`은 포인터를 와이드 문자열 결과로 반환합니다. 오류 반환 값이 없습니다.  
  
## <a name="remarks"></a>설명  
 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [asctime_s, _wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)를 참조하세요.  
  
 `asctime` 함수는 구조체로 저장된 시간을 문자열로 변환합니다. `timeptr` 값은 일반적으로 `gmtime` 또는 `localtime`에 대한 호출에서 가져옵니다. 이 두 시간은 TIME.H에 정의된 `tm` 구조체로 포인터를 반환합니다.  
  
|timeptr 멤버|값|  
|--------------------|-----------|  
|`tm_hour`|자정 (0-23)|  
|`tm_isdst`|일광 절약 시간이 적용되면 양수, 일광 절약 시간이 적용되지 않으면 0, 일광 절약 시간의 상태를 알 수 없으면 음수입니다. C 런타임 라이브러리에서는 DST(일광 절약 시간) 계산 구현을 위한 미국의 규칙이 사용된다고 가정합니다.|  
|`tm_mday`|월 (1-31)의 날짜|  
|`tm_min`|분 후에 시간 (0-59)|  
|`tm_mon`|월 (0-11; 1 월 = 0)|  
|`tm_sec`|초 후 분 (0-59)|  
|`tm_wday`|요일 (0-6; 일요일 = 0)|  
|`tm_yday`|(0-365; 연간 일자 1 월 1 일 = 0)|  
|`tm_year`|연도(현재 연도 빼기 1900)|  
  
 또한 변환된 문자열은 현지 표준 시간대 설정에 따라 조정됩니다. 현지 시간 구성에 대한 정보는 [time](../../c-runtime-library/reference/time-time32-time64.md), [_ftime](../../c-runtime-library/reference/ftime-ftime32-ftime64.md) 및 [localtime](../../c-runtime-library/reference/localtime-localtime32-localtime64.md) 함수를 참조하고 표준 시간대 환경 및 전역 변수 정의에 대한 정보는 [_tzset](../../c-runtime-library/reference/tzset.md) 함수를 참조하세요.  
  
 `asctime`에 의해 생성된 문자열 결과는 정확히 26자를 포함하며 `Wed Jan 02 02:03:55 1980\n\0` 형식을 갖습니다. 24시간제가 사용됩니다. 모든 필드에는 상수 너비가 있습니다. 줄 바꿈 문자 및 null 문자는 문자열의 마지막 두 자리를 차지합니다. `asctime`은 정적으로 할당된 단일 버퍼를 사용하여 반환 문자열을 보관합니다. 이 함수를 호출할 때마다 이전 호출의 결과가 삭제됩니다.  
  
 `_wasctime`은 `asctime`의 와이드 문자 버전입니다. 그렇지 않으면 `_wasctime`과 `asctime`이 동일하게 작동합니다.  
  
 이러한 함수는 해당 함수 매개 변수의 유효성을 검사합니다. `timeptr`이 null 포인터이거나 범위를 벗어난 값을 포함하는 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용된 경우 함수가 `NULL`를 반환하며 `errno`를 `EINVAL`로 설정합니다.  
  
### <a name="generic-text-routine-mapping"></a>제네릭 텍스트 루틴 매핑  
  
|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tasctime`|`asctime`|`asctime`|`_wasctime`|  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`asctime`|\<time.h>|  
|`_wasctime`|\<time.h> 또는 \<wchar.h>|  
  
## <a name="example"></a>예  
 이 프로그램은 시스템 시간을 정수(Long) `aclock`에 배치하고, 이를 `newtime` 구조체로 전환한 다음, `asctime` 함수를 사용하여 출력용 문자열 형식으로 변환합니다.  
  
```  
// crt_asctime.c  
// compile with: /W3  
  
#include <time.h>  
#include <stdio.h>  
  
int main( void )  
{  
    struct tm   *newTime;  
    time_t      szClock;  
  
    // Get time in seconds  
    time( &szClock );  
  
    // Convert time to struct tm form   
    newTime = localtime( &szClock );  
  
    // Print local time as a string.  
    printf_s( "Current date and time: %s", asctime( newTime ) ); // C4996  
    // Note: asctime is deprecated; consider using asctime_s instead  
}  
```  
  
```Output  
Current date and time: Sun Feb 03 11:38:58 2002  
```  
  
## <a name="see-also"></a>참고 항목  
 [시간 관리](../../c-runtime-library/time-management.md)   
 [ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [_tzset](../../c-runtime-library/reference/tzset.md)   
 [asctime_s, _wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)