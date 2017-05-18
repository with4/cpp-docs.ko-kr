---
title: mktime, _mktime32, _mktime64 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mktime32
- mktime
- _mktime64
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
- mktime
- _mktime64
dev_langs:
- C++
helpviewer_keywords:
- _mktime32 function
- mktime function
- time functions
- mktime64 function
- converting times
- mktime32 function
- _mktime64 function
- time, converting
ms.assetid: 284ed5d4-7064-48a2-bd50-15effdae32cf
caps.latest.revision: 25
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
ms.openlocfilehash: ced40f391f4a4085531d624acc45094e06e1f0a8
ms.contentlocale: ko-kr
ms.lasthandoff: 04/01/2017

---
# <a name="mktime-mktime32-mktime64"></a>mktime, _mktime32, _mktime64
현지 시간을 달력 값으로 변환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
time_t mktime(  
   struct tm *timeptr   
);  
__time32_t _mktime32(  
   struct tm *timeptr   
);  
__time64_t _mktime64(  
   struct tm *timeptr   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 *timeptr*  
 시간 구조에 대한 포인터입니다. [asctime](../../c-runtime-library/reference/asctime-wasctime.md)을 참조하세요.  
  
## <a name="return-value"></a>반환 값  
 `_mktime32`는 [time_t](../../c-runtime-library/standard-types.md) 형식의 값으로 인코딩된 지정한 달력 시간을 반환합니다. 경우 *timeptr* 자정 1970 년 1 월 1 일 이전의 날짜를 참조 하거나 해당 달력 시간을 표현할 수 없는 경우 `_mktime32` 형식으로 캐스팅 하는-1을 반환 `time_t`합니다. 사용 하는 경우 `_mktime32` 쓰고 *timeptr* 23시 59분: 59 2038 년 1 월 18 일, utc (협정 세계시) 이후 날짜는 참조 형식으로 캐스팅 하는-1을 반환 합니다 `time_t`합니다.  
  
 `_mktime64`형식으로 캐스팅 하는-1을 반환 하는 `__time64_t` 경우 *timeptr* 23시 59분: 59를 3000 년 12 월 31 일 UTC 이후 날짜를 참조 합니다.  
  
## <a name="remarks"></a>주의  
 `mktime`, `_mktime32` 및 `_mktime64` 함수는 정규화된 값을 사용하여 *timeptr*로 가리키는 제공된 시간 구조(불완전할 수 있음)를 완전히 정의된 구조로 변환한 다음 `time_t` 달력 시간 값으로 변환합니다. 변환된 시간은 [time](../../c-runtime-library/reference/time-time32-time64.md) 함수가 반환한 값과 인코딩이 동일합니다. *timeptr* 구조의 `tm_wday` 및 `tm_yday` 구성 요소가 가진 원래 값이 무시되며 다른 구성 요소의 원래 값은 정상 범위로 제한되지 않습니다.  
  
 `mktime`은 `_mktime64`와 동일한 인라인 함수로 `_USE_32BIT_TIME_T`를 정의하지 않으면 `_mktime32`와 동일합니다.  
  
 UTC로 조정 후 `_mktime32`는 UTC로 1970년 1월 1일 자정에서 2038년 1월 18일 오후 11시 59분 59초까지의 날짜를 처리합니다. `_mktime64`는 1970년 1월 1일 자정에서 3000년 12월 31일 23:59:59까지의 날짜를 처리합니다. 지정한 날짜가 범위 내에 있더라도 이처럼 조정하면 이러한 함수가 -1을 반환할 할 수 있습니다(`time_t`, `__time32_t` 또는 `__time64_t`로 캐스트). 예를 들어 UTC보다 2시간 빠른 이집트의 카이로에 있으면 *timeptr*에 지정한 날짜에서 먼저 2시간을 뺍니다. 그러면 해당 날짜가 범위를 벗어날 수 있습니다.  
  
 이러한 함수는 tm 구조의 유효성을 검사하고 시간 구조를 채우는 데 사용할 수 있습니다. 성공하면 이러한 함수는 `tm_wday` 및 `tm_yday`의 값을 적절하게 설정하고, 지정한 달력 시간을 표현하도록 다른 구성 요소를 설정하지만 해당 값을 강제로 정상 범위 내에 있도록 합니다. `tm_mday` 및 `tm_mon`가 결정될 때까지 `tm_year`의 최종 값은 설정되지 않습니다. `tm` 구조 시간을 지정하면 `tm_isdst` 필드를 다음과 같이 설정합니다.  
  
-   0은 표준 시간이 적용 중임을 나타냅니다.  
  
-   0보다 큰 값은 일광 절약 시간이 적용 중임을 나타냅니다.  
  
-   0보다 작은 값은 C 런타임 라이브러리 코드가 표준 시간 또는 일광 절약 시간이 적용 중인지 여부를 계산하도록 합니다.  
  
 C 런타임 라이브러리는 [TZ](../../c-runtime-library/reference/tzset.md) 환경 변수에서 일광 절약 시간 동작을 결정합니다. `TZ`를 설정하지 않으면 Win32 API 호출인 [GetTimeZoneInformation](http://msdn.microsoft.com/library/windows/desktop/ms724421.aspx)을 사용하여 운영 체제에서 일광 절약 시간 정보를 가져옵니다. 이러한 정보를 가져오지 못하면 라이브러리에서는 일광 절약 시간 계산 구현을 위한 미국의 규칙이 사용된다고 가정합니다. `tm_isdst`는 필수 필드입니다. 이 필드를 설정하지 않으면 해당 값이 정의되지 않고 이러한 함수의 반환 값을 예측할 수 없습니다. *timeptr*이 `asctime`, `gmtime` 또는 `localtime` 함수나 이러한 함수의 변형에 대한 이전 호출에서 반환한 `tm` 구조를 가리키면 `tm_isdst` 필드에 올바른 값이 포함됩니다.  
  
 `gmtime` 및 `localtime`(그리고 `_gmtime32`, `_gmtime64`, `_localtime32` 및 `_localtime64`)는 변환을 위해 스레드당 단일 버퍼를 사용합니다. 이 버퍼를 `mktime`, `_mktime32` 또는 `_mktime64`에 제공하면 이전 내용이 소멸됩니다.  
  
 이러한 함수는 해당 함수 매개 변수의 유효성을 검사합니다. *timeptr*이 null 포인터인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용한 경우 이러한 함수가 -1을 반환하고 `errno`를 `EINVAL`로 설정합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`mktime`|\<time.h>|  
|`_mktime32`|\<time.h>|  
|`_mktime64`|\<time.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="libraries"></a>라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## <a name="example"></a>예제  
  
```  
// crt_mktime.c  
/* The example takes a number of days  
 * as input and returns the time, the current  
 * date, and the specified number of days.  
 */  
  
#include <time.h>  
#include <stdio.h>  
  
int main( void )  
{  
   struct tm  when;  
   __time64_t now, result;  
   int        days;  
   char       buff[80];  
  
   time( &now );  
   _localtime64_s( &when, &now );  
   asctime_s( buff, sizeof(buff), &when );  
   printf( "Current time is %s\n", buff );  
   days = 20;  
   when.tm_mday = when.tm_mday + days;  
   if( (result = mktime( &when )) != (time_t)-1 ) {  
      asctime_s( buff, sizeof(buff), &when );  
      printf( "In %d days the time will be %s\n", days, buff );  
   } else  
      perror( "mktime failed" );  
}  
```  
  
## <a name="sample-output"></a>샘플 출력  
  
```  
Current time is Fri Apr 25 13:34:07 2003  
  
In 20 days the time will be Thu May 15 13:34:07 2003  
```  
  
## <a name="see-also"></a>참고 항목  
 [시간 관리](../../c-runtime-library/time-management.md)   
 [asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [_mkgmtime, _mkgmtime32, _mkgmtime64](../../c-runtime-library/reference/mkgmtime-mkgmtime32-mkgmtime64.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)
