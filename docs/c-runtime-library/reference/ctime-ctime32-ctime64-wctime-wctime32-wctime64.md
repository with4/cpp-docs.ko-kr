---
title: "ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _ctime64
- _wctime32
- ctime
- _wctime64
- _ctime32
- _wctime
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
- _wctime64
- _ctime32
- _tctime
- _wctime
- _wctime32
- _tctime64
- _ctime64
- ctime
dev_langs:
- C++
helpviewer_keywords:
- tctime64 function
- _ctime32 function
- ctime32 function
- _wctime function
- wctime64 function
- _tctime64 function
- _tctime32 function
- _ctime64 function
- _wctime64 function
- ctime function
- wctime32 function
- ctime64 function
- _wctime32 function
- _tctime function
- tctime32 function
- tctime function
- wctime function
- time, converting
ms.assetid: 2423de37-a35c-4f0a-a378-3116bc120a9d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c3154b71654f0b4fc944daa94a354db32c981c2f
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="ctime-ctime32-ctime64-wctime-wctime32-wctime64"></a>ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64
시간 값을 문자열로 변환하고 현지 표준 시간대 설정에 맞게 조정합니다. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](../../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
char *ctime(   
   const time_t *timer   
);  
char *_ctime32(   
   const __time32_t *timer )  
;  
char *_ctime64(   
   const __time64_t *timer )  
;  
wchar_t *_wctime(   
   const time_t *timer   
);  
wchar_t *_wctime32(   
   const __time32_t *timer  
);  
wchar_t *_wctime64(   
   const __time64_t *timer   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `timer`  
 저장된 시간에 대한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 문자열 결과에 대한 포인터입니다. 다음의 경우 `NULL`이 반환됩니다.  
  
-   `time`은 1970년 1월 1일(UTC) 자정 이전의 날짜를 나타냅니다.  
  
-   `_ctime32` 또는 `_wctime32`를 사용하는 경우 `time`은 2038년 1월 18일(UTC) 23:59:59 이후 날짜를 나타냅니다.  
  
-   `_ctime64` 또는 `_wctime64`를 사용하는 경우 `time`은 3000년 12월 31일(UTC) 23:59:59 이후 날짜를 나타냅니다.  
  
 `ctime`은 `_ctime64`로 계산되는 인라인 함수이며 `time_t`는 `__time64_t`와 동일합니다. 컴파일러에서 `time_t`를 이전의 32비트 `time_t`로 해석하게 해야 하는 경우 `_USE_32BIT_TIME_T`를 정의할 수 있습니다. 이렇게 하면 `ctime`가 `_ctime32`로 계산됩니다. 2038년 1월 18일 이후에는 응용 프로그램에서 오류가 발생할 수 있으므로 이 방식은 사용하지 않는 것이 좋으며, 64비트 플랫폼에서는 이러한 방식이 허용되지 않습니다.  
  
## <a name="remarks"></a>설명  
 `ctime` 함수는 [time_t](../../c-runtime-library/standard-types.md) 값으로 저장된 시간 값을 문자열로 변환합니다. `timer` 값은 일반적으로 UTC(협정 세계시) 기준 1970년 1월 1일 자정(00:00:00) 이후에 경과된 시간(초)을 반환하는 [time](../../c-runtime-library/reference/time-time32-time64.md)을 호출하여 가져옵니다. 반환 값 문자열은 정확히 26자를 포함하며 그 형식은 다음과 같습니다.  
  
```  
Wed Jan 02 02:03:55 1980\n\0  
```  
  
 24시간제가 사용됩니다. 모든 필드에는 상수 너비가 있습니다. 줄 바꿈 문자('\n') 및 null 문자('\0')는 문자열의 마지막 두 자리를 차지합니다.  
  
 또한 변환된 문자열은 현지 표준 시간대 설정에 따라 조정됩니다. 현지 시간을 구성하는 방법에 대한 자세한 내용은 `time`, [_ftime](../../c-runtime-library/reference/ftime-ftime32-ftime64.md) 및 [localtime](../../c-runtime-library/reference/localtime-localtime32-localtime64.md) 함수를 참조하고, 표준 시간대 환경 및 전역 변수를 정의하는 방법에 대한 자세한 내용은 [_tzset](../../c-runtime-library/reference/tzset.md) 함수를 참조하세요.  
  
 `ctime`을 호출하면 `gmtime` 및 `localtime` 함수에서 사용하는 단일 정적 할당 버퍼가 수정됩니다. 이러한 루틴 중 하나를 호출할 때마다 이전 호출의 결과가 삭제됩니다. `ctime`은 `asctime` 함수와 정적 버퍼를 공유합니다. 따라서 `ctime`을 호출하면 `asctime`, `localtime` 또는 `gmtime`에 대한 이전 호출의 결과가 삭제됩니다.  
  
 `_wctime` 및 `_wctime64`는 `ctime` 및 `_ctime64`의 와이드 문자 버전이며, 와이드 문자 문자열에 대한 포인터를 반환합니다. 그 외에는 `_ctime64`, `_wctime` 및 `_wctime64`가 `ctime`과 동일하게 작동합니다.  
  
 이러한 함수는 해당 함수 매개 변수의 유효성을 검사합니다. `timer`가 null 포인터이거나 timer 값이 음수인 경우 이러한 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 계속해서 실행하도록 허용된 경우 이 함수는 `NULL`을 반환하며 `errno`를 `EINVAL`로 설정합니다.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑  
  
|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tctime`|`ctime`|`ctime`|`_wctime`|  
|`_tctime32`|`_ctime32`|`_ctime32`|`_wctime32`|  
|`_tctime64`|`_ctime64`|`_ctime64`|`_wctime64`|  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`ctime`|\<time.h>|  
|`_ctime32`|\<time.h>|  
|`_ctime64`|\<time.h>|  
|`_wctime`|\<time.h> 또는 \<wchar.h>|  
|`_wctime32`|\<time.h> 또는 \<wchar.h>|  
|`_wctime64`|\<time.h> 또는 \<wchar.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## <a name="example"></a>예  
  
```  
// crt_ctime64.c  
// compile with: /W3  
/* This program gets the current  
 * time in _time64_t form, then uses ctime to  
 * display the time in string form.  
 */  
  
#include <time.h>  
#include <stdio.h>  
  
int main( void )  
{  
   __time64_t ltime;  
  
   _time64( &ltime );  
   printf( "The time is %s\n", _ctime64( &ltime ) ); // C4996  
   // Note: _ctime64 is deprecated; consider using _ctime64_s  
}  
```  
  
```Output  
The time is Wed Feb 13 16:04:43 2002  
```  
  
## <a name="see-also"></a>참고 항목  
 [시간 관리](../../c-runtime-library/time-management.md)   
 [asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s](../../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)   
 [_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)