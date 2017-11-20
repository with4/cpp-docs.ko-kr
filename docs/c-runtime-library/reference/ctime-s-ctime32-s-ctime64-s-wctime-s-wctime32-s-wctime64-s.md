---
title: "ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ctime64_s
- _wctime32_s
- ctime_s
- _wctime64_s
- _ctime32_s
- _wctime_s
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
- ctime64_s
- _ctime32_s
- _tctime32_s
- _ctime64_s
- _wctime_s
- _tctime_s
- _tctime64_s
- ctime_s
- ctime32_s
dev_langs: C++
helpviewer_keywords:
- _wctime32_s function
- ctime64_s function
- _tctime64_s function
- _wctime_s function
- tctime_s function
- _wctime64_s function
- ctime_s function
- ctime32_s function
- _ctime64_s function
- tctime64_s function
- wctime64_s function
- wctime_s function
- _tctime_s function
- tctime32_s function
- wctime32_s function
- time, converting
- _ctime32_s function
- _tctime32_s function
ms.assetid: 36ac419a-8000-4389-9fd8-d78b747a009b
caps.latest.revision: "27"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: aa59a7855942b9a67db41038261cc8eb5f7da71d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="ctimes-ctime32s-ctime64s-wctimes-wctime32s-wctime64s"></a>ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s
시간 값을 문자열로 변환하고 현지 표준 시간대 설정에 맞게 조정합니다. 이러한 함수는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 있는 [ctime, _ctime64, _wctime, _wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)의 버전입니다.  
  
## <a name="syntax"></a>구문  
  
```  
errno_t ctime_s(   
   char* buffer,  
   size_t numberOfElements,  
   const time_t *time   
);  
errno_t _ctime32_s(   
   char* buffer,  
   size_t numberOfElements,  
   const __time32_t *time   
);  
errno_t _ctime64_s(   
   char* buffer,  
   size_t numberOfElements,  
   const __time64_t *time )  
;  
errno_t _wctime_s(   
   wchar_t* buffer,  
   size_t numberOfElements,  
   const time_t *time   
);  
errno_t _wctime32_s(   
   wchar_t* buffer,  
   size_t numberOfElements,  
   const __time32_t *time   
);  
errno_t _wctime64_s(   
   wchar_t* buffer,  
   size_t numberOfElements,  
   const __time64_t *time   
);  
template <size_t size>  
errno_t _ctime32_s(   
   char (&buffer)[size],  
   const __time32_t *time   
); // C++ only  
template <size_t size>  
errno_t _ctime64_s(   
   char (&buffer)[size],  
   const __time64_t *time  
); // C++ only  
template <size_t size>  
errno_t _wctime32_s(   
   wchar_t (&buffer)[size],  
   const __time32_t *time   
); // C++ only  
template <size_t size>  
errno_t _wctime64_s(   
   wchar_t (&buffer)[size],  
   const __time64_t *time   
); // C++ only  
```  
  
#### <a name="parameters"></a>매개 변수  
 [out] `buffer`  
 26자를 포함할 만큼 충분히 커야 합니다. 문자 문자열 결과에 대 한 포인터 또는 `NULL` 경우:  
  
-   `time`은 1970년 1월 1일(UTC) 자정 이전의 날짜를 나타냅니다.  
  
-   `_ctime32_s` 또는 `_wctime32_s`를 사용하는 경우 `time`은 2038년 1월 18일(UTC) 23:59:59 이후 날짜를 나타냅니다.  
  
-   `_ctime64_s` 또는 `_wctime64_s`를 사용하는 경우 `time`은 3000년 12월 31일(UTC) 23:59:59 이후 날짜를 나타냅니다.  
  
-   `_ctime_s` 또는 `_wctime_s`를 사용하는 경우 이러한 함수는 이전 함수에 대한 래퍼입니다. 설명 부분을 참조하세요.  
  
 [in] `numberOfElements`  
 버퍼의 크기입니다.  
  
 [in] `time`  
 저장된 시간에 대한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 성공할 경우 0입니다. 잘못된 매개 변수로 인해 실패할 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속 실행하도록 허용된 경우 오류 코드가 반환됩니다. 오류 코드는 ERRNO.H에 정의됩니다. 이러한 오류의 목록을 보려면 [errno](../../c-runtime-library/errno-constants.md)를 참조하세요. 각 오류 조건에 대해 throw되는 실제 오류 코드가 다음 표에 나와 있습니다.  
  
## <a name="error-conditions"></a>오류 조건  
  
|`buffer`|`numberOfElements`|`time`|반환|`buffer`의 값|  
|--------------|------------------------|------------|------------|-----------------------|  
|`NULL`|모두|모두|`EINVAL`|수정 안 됨|  
|`NULL` 아님(유효한 메모리를 가리킴)|0|모두|`EINVAL`|수정 안 됨|  
|`NULL` 아님|0< 크기 < 26|모두|`EINVAL`|빈 문자열|  
|`NULL` 아님|>= 26|NULL|`EINVAL`|빈 문자열|  
|`NULL` 아님|>= 26|< 0|`EINVAL`|빈 문자열|  
  
## <a name="remarks"></a>설명  
 `ctime_s` 함수는 [time_t](../../c-runtime-library/standard-types.md) 구조체로 저장된 시간 값을 문자열로 변환합니다. `time` 값은 일반적으로 UTC(협정 세계시) 기준 1970년 1월 1일 자정(00:00:00) 이후에 경과된 시간(초)을 반환하는 [time](../../c-runtime-library/reference/time-time32-time64.md)을 호출하여 가져옵니다. 반환 값 문자열은 정확히 26자를 포함하며 그 형식은 다음과 같습니다.  
  
```  
Wed Jan 02 02:03:55 1980\n\0  
```  
  
 24시간제가 사용됩니다. 모든 필드에는 상수 너비가 있습니다. 줄 바꿈 문자('\n') 및 null 문자('\0')는 문자열의 마지막 두 자리를 차지합니다.  
  
 또한 변환된 문자열은 현지 표준 시간대 설정에 따라 조정됩니다. 현지 시간을 구성하는 방법에 대한 자세한 내용은 `time`, [_ftime](../../c-runtime-library/reference/ftime-ftime32-ftime64.md) 및 [localtime32_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md) 함수를 참조하고, 표준 시간대 환경 및 전역 변수를 정의하는 방법에 대한 자세한 내용은 [_tzset](../../c-runtime-library/reference/tzset.md) 함수를 참조하세요.  
  
 `_wctime32_s` 및 `_wctime64_s`는 `_ctime32_s` 및 `_ctime64_s`의 와이드 문자 버전이며, 와이드 문자 문자열에 대한 포인터를 반환합니다. 그 외에는 `_ctime64_s`, `_wctime32_s` 및 `_wctime64_s`가 `_ctime32_s`와 동일하게 작동합니다.  
  
 `ctime_s`는 `_ctime64_s`로 계산되는 인라인 함수이며 `time_t`는 `__time64_t`와 동일합니다. 컴파일러에서 `time_t`를 이전의 32비트 `time_t`로 해석하게 해야 하는 경우 `_USE_32BIT_TIME_T`를 정의할 수 있습니다. 이렇게 하면 `ctime_s`가 `_ctime32_s`로 계산됩니다. 2038년 1월 18일 이후에는 응용 프로그램에서 오류가 발생할 수 있으므로 이 방식은 사용하지 않는 것이 좋으며, 64비트 플랫폼에서는 이러한 방식이 허용되지 않습니다.  
  
 C++에서는 템플릿 오버로드를 통해 이러한 함수를 사용하는 것이 더욱 간단해집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으므로 크기 인수를 지정할 필요가 없습니다. 자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)를 참조하세요.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tctime_s`|`ctime_s`|`ctime_s`|`_wctime_s`|  
|`_tctime32_s`|`_ctime32_s`|`_ctime32_s`|`_wctime32_s`|  
|`_tctime64_s`|`_ctime64_s`|`_ctime64_s`|`_wctime64_s`|  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`ctime_s`, `_ctime32_s`, `_ctime64_s`|\<time.h>|  
|`_wctime_s`, `_wctime32_s`, `_wctime64_s`|\<time.h> 또는 \<wchar.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="libraries"></a>라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## <a name="example"></a>예제  
  
```  
// crt_wctime_s.c  
/* This program gets the current  
 * time in time_t form and then uses _wctime_s to  
 * display the time in string form.  
 */  
  
#include <time.h>  
#include <stdio.h>  
  
#define SIZE 26  
  
int main( void )  
{  
   time_t ltime;  
   wchar_t buf[SIZE];  
   errno_t err;  
  
   time( &ltime );  
  
   err = _wctime_s( buf, SIZE, &ltime );  
   if (err != 0)  
   {  
      printf("Invalid Arguments for _wctime_s. Error Code: %d\n", err);  
   }  
   wprintf_s( L"The time is %s\n", buf );  
}  
```  
  
## <a name="sample-output"></a>샘플 출력  
  
```  
The time is Fri Apr 25 13:03:39 2003  
```  
  
## <a name="see-also"></a>참고 항목  
 [시간 관리](../../c-runtime-library/time-management.md)   
 [asctime_s, _wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](../../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)   
 [_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime_s, _gmtime32_s, _gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime_s, _localtime32_s, _localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)