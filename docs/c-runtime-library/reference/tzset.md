---
title: _tzset | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _tzset
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
- _tzset
dev_langs:
- C++
helpviewer_keywords:
- _tzset function
- time environment variables
- environment variables, setting time
ms.assetid: 3f6ed537-b414-444d-b272-5dd377481930
caps.latest.revision: 23
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 669b7d41234c21c3fb4e9a1a28f6b8d1a33c036b
ms.contentlocale: ko-kr
ms.lasthandoff: 04/04/2017

---
# <a name="tzset"></a>_tzset
시간 환경 변수를 설정합니다.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은                  [/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
void _tzset( void );  
```  
  
## <a name="remarks"></a>설명  
 `_tzset` 함수는 환경 변수 `TZ` 의 현재 설정을 사용하여 세 개의 전역 변수 `_daylight`, `_timezone`및 `_tzname`에 값을 할당합니다. 이러한 변수는 [_ftime](../../c-runtime-library/reference/ftime-ftime32-ftime64.md) 및 [localtime](../../c-runtime-library/reference/localtime-localtime32-localtime64.md) 함수에서 UTC(협정 세계시)를 현지 시간으로 수정하는 데 사용되며, `time` 함수가 시스템 시간에서 UTC를 계산하는 데 사용됩니다. 다음 구문을 사용하여 `TZ` 환경 변수를 설정합니다.  
  
 `set` `TZ`=`tzn`[+ &#124; -]`hh`[`:``mm`[`:``ss`] ][`dzn`]  
  
 `tzn`  
 3자의 표준 시간대 이름(예: PST)입니다. 현지 시간에서 UTC로의 올바른 오프셋을 지정해야 합니다.  
  
 `hh`  
 UTC와 현지 시간 사이의 차이(시간)입니다. 양수 값에 선택적인 (+) 부호입니다.  
  
 `mm`  
 분. 콜론( `hh` )으로`:`와 구분합니다.  
  
 `ss`  
 초. 콜론( `mm` )으로`:`와 구분합니다.  
  
 `dzn`  
 3자의 일광 절약 시간 표준 시간대(예: PDT)입니다. 일광 절약 시간이 현지에서 적용되지 않는 경우 `TZ` 에 대한 값 없이 `dzn`설정합니다. C 런타임 라이브러리에서는 DST(일광 절약 시간) 계산 구현을 위한 미국의 규칙이 사용된다고 가정합니다.  
  
> [!NOTE]
>  계산할 때는 시간 차이의 부호에 주의해야 합니다. 시간 차이는 현지 시간에서 UTC로의 오프셋(역방향 아님)이므로 부호가 직관적으로 예상하는 것과 반대일 수 있습니다. UTC보다 빠른 표준 시간대의 경우 시간 차이가 음수이고, UTC보다 늦은 표준 시간대의 경우 차이가 양수입니다.  
  
 예를 들어 현재 독일의 표준 시간대에 해당하도록 `TZ` 환경 변수를 설정하려면 명령줄에 다음을 입력합니다.  
  
```  
set TZ=GST-1GDT  
```  
  
 이 명령은 GST를 사용하여 독일 표준 시간을 나타내고, UTC는 독일보다 한 시간 뒤, 즉 독일은 UTC보다 한 시간 앞이라고 가정하며, 독일은 일광 절약 시간을 준수한다고 가정합니다.  
  
 경우는 `TZ` 값을 설정 하지 않으면 `_tzset` 운영 체제에서 지정 된 표준 시간대 정보를 사용 하려고 시도 합니다. Windows 운영 체제에서 이 정보는 제어판의 날짜/시간 응용 프로그램에 지정되어 있습니다. `_tzset` 에서 이 정보를 가져올 수 없는 경우 기본적으로 태평양 표준 시간대를 의미하는 PST8PDT를 사용합니다.  
  
 `TZ` 환경 변수 값에 따라 `_daylight`을 호출할 때 다음 값이 전역 변수 `_timezone`, `_tzname` 및 `_tzset` 에 할당됩니다.  
  
|전역 변수|설명|기본값|  
|---------------------|-----------------|-------------------|  
|`_daylight`|일광 절약 시간 표준 시간대가 `TZ` 설정에 지정된 경우 0이 아닌 값이고, 그러지 않으면 0입니다.|1|  
|`_timezone`|현지 시간과 UTC 사이의 차이(초)입니다.|28800(28800초 = 8시간)|  
|`_tzname`[0]|`TZ` 환경 변수에서 표준 시간대 이름의 문자열 값이며, `TZ` 가 설정되지 않은 경우 비어 있습니다.|PST|  
|`_tzname`[1]|일광 절약 시간 표준 시간대의 문자열 값이며, `TZ` 환경 변수에서 일광 절약 시간 표준 시간대가 생략된 경우 비어 있습니다.|PDT|  
  
 `_daylight` 에 대해 앞의 표에 표시된 기본값 및 `_tzname` 배열은 "PST8PDT"에 해당합니다. DST 영역이 `TZ` 환경 변수에서 생략되고 `_daylight` 의 값이 0이면 `_ftime`, `gmtime`및 `localtime` 함수는 DST 플래그에 대해 0을 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_tzset`|\<time.h>|  
  
 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```  
// crt_tzset.cpp  
// This program uses _tzset to set the global variables  
// named _daylight, _timezone, and _tzname. Since TZ is  
// not being explicitly set, it uses the system time.  
  
#include <time.h>  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
    _tzset();  
    int daylight;  
    _get_daylight( &daylight );  
    printf( "_daylight = %d\n", daylight );  
    long timezone;  
    _get_timezone( &timezone );  
    printf( "_timezone = %ld\n", timezone );  
    size_t s;  
    char tzname[100];  
    _get_tzname( &s, tzname, sizeof(tzname), 0 );  
    printf( "_tzname[0] = %s\n", tzname );  
    exit( 0 );  
}  
```  
  
```Output  
_daylight = 1  
_timezone = 28800  
_tzname[0] = Pacific Standard Time  
```  
  
## <a name="see-also"></a>참고 항목  
 [시간 관리](../../c-runtime-library/time-management.md)   
 [asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [_utime, _utime32, _utime64, _wutime, _wutime32, _wutime64](../../c-runtime-library/reference/utime-utime32-utime64-wutime-wutime32-wutime64.md)
