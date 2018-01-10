---
title: strftime, wcsftime, _strftime_l, _wcsftime_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- strftime
- _wcsftime_l
- _strftime_l
- wcsftime
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
- _tcsftime
- strftime
- wcsftime
dev_langs: C++
helpviewer_keywords:
- _strftime_l function
- strftime function
- tcsftime function
- _wcsftime_l function
- wcsftime function
- _tcsftime function
- time strings
ms.assetid: 6330ff20-4729-4c4a-82af-932915d893ea
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 785ad16e8f86f74252c4391044d2def96091fe61
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="strftime-wcsftime-strftimel-wcsftimel"></a>strftime, wcsftime, _strftime_l, _wcsftime_l
시간 문자열 서식을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
size_t strftime(  
   char *strDest,  
   size_t maxsize,  
   const char *format,  
   const struct tm *timeptr   
);  
size_t _strftime_l(  
   char *strDest,  
   size_t maxsize,  
   const char *format,  
   const struct tm *timeptr,  
   _locale_t locale  
);  
size_t wcsftime(  
   wchar_t *strDest,  
   size_t maxsize,  
   const wchar_t *format,  
   const struct tm *timeptr   
);  
size_t _wcsftime_l(  
   wchar_t *strDest,  
   size_t maxsize,  
   const wchar_t *format,  
   const struct tm *timeptr,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `strDest`  
 출력 문자열입니다.  
  
 `maxsize`  
 문자 단위로 측정한 버퍼의 크기`strDest`입니다(`char` 또는 `wchart_t`).  
  
 `format`  
 형식 컨트롤 문자열입니다.  
  
 `timeptr`  
 `tm` 데이터 구조입니다.  
  
 `locale`  
 사용할 로캘입니다.  
  
## <a name="return-value"></a>반환 값  
 `strftime`은 `strDest`에 배치되는 문자 수를 반환하고 `wcsftime`은 해당하는 와이드 문자의 수를 반환합니다.  
  
 종료 null을 포함한 문자의 총 수가 `maxsize`보다 많으면 `strftime` 및 `wcsftime`은 둘 다 0을 반환하며 `strDest`의 내용은 결정되지 않습니다.  
  
 `strDest`의 문자 수는 `format`의 리터럴 문자 수 및 서식 코드를 통해 `format`에 추가할 수 있는 문자와 동일합니다. 문자열의 종료 null은 반환 값 계산에 포함되지 않습니다.  
  
## <a name="remarks"></a>설명  
 `strftime` 및 `wcsftime` 함수 형식은 `tm` 시간 값에서 `timeptr` 에 제공 된 따라 `format` 인수와 저장소 버퍼에 결과 `strDest`합니다. 문자열에는 최대 `maxsize`개의 문자가 배치됩니다. `timeptr` 구조체의 필드에 대한 설명은 [asctime](../../c-runtime-library/reference/asctime-wasctime.md)을 참조하세요. `wcsftime`은 `strftime`에 해당하는 와이드 문자 버전이고 해당 문자열 포인터 인수는 와이드 문자열을 가리킵니다. 그 외의 경우에는 이들 함수가 동일하게 작동합니다.  
  
> [!NOTE]
>  Visual C++ 2005 이전 버전의 설명서에서는 `wcsftime`의 `format` 매개 변수 데이터 형식이 `const wchar_t *`인 것으로 설명되어 있었으나 실제 `format` 데이터 형식의 구현은 `const char *`였습니다. 구현에서 `format` 데이터 형식을 이전 및 현재 설명서, 즉, 반영 하도록 업데이트 되었습니다 `const wchar_t *`합니다.  
  
 이 함수는 해당 매개 변수의 유효성을 검사합니다. 경우 `strDest`, `format`, 또는 `timeptr` 가 null 포인터인 경우는 `tm` 데이터 구조에서 해결 `timeptr` (예를 들어 시간 또는 날짜 범위를 벗어난 값 포함), 유효 하지 또는 경우에는 `format` 문자열 잘못 된 형식 지정 코드를 보려면 포함에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 계속해서 실행하도록 허용한 경우 함수는 0을 반환하고 `errno`를 `EINVAL`로 설정합니다.  
  
### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑  
  
|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcsftime`|`strftime`|`strftime`|`wcsftime`|  
  
 `format` 인수는 하나 이상의 코드로 구성됩니다. `printf`에서와 같이 서식 코드 앞에는 퍼센트 기호(`%`)가 붙습니다. 로 시작 하지 않는 문자 `%` 에 변경 되지 않은 복사 `strDest`합니다. 현재 로캘의 `LC_TIME` 범주가 `strftime`의 출력 서식에 영향을 줍니다. `LC_TIME`에 대한 자세한 내용은 [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)을 참조하세요. `_l` 접미사가 없는 함수는 현재 설정된 로캘을 사용합니다. 이러한 함수의 `_l` 접미사가 있는 버전은 로캘을 매개 변수로 사용하며 현재 설정된 로캘 대신 해당 로캘을 사용한다는 점을 제외하면 동일합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.  
  
 아래에는 `strftime`의 서식 코드가 나와 있습니다.  
  
 `%a`  
 요일 약어  
  
 `%A`  
 전체 요일 이름  
  
 `%b`  
 월 약어  
  
 `%B`  
 전체 월 이름  
  
 `%c`  
 로캘에 적합한 날짜 및 시간 표현  
  
 `%d`  
 10 진수 (01-31)로 월의 일  
  
 `%H`  
 24 시간 형식의 시간 (00-23)  
  
 `%I`  
 12 시간 형식의 시간 (01-12)  
  
 `%j`  
 10 진수 (001-366)으로 연간 일자  
  
 `%m`  
 10 진수 (01-12)로 월  
  
 `%M`  
 숫자 형식의 분 (00-59)  
  
 `%p`  
 현재 로캘의 오전/오후 12시간제 표시기  
  
 `%S`  
 숫자 형식의 두 번째 (00-59)  
  
 `%U`  
 일요일이 주의 첫 번째 요일 숫자 형식의 연도의 주 (00-53)  
  
 `%w`  
 요일 숫자 (0-6; 일요일은 0 임)  
  
 `%W`  
 첫 번째 요일 월요일 숫자 형식의 연도의 주 (00-53)  
  
 `%x`  
 현재 로캘의 날짜 표현  
  
 `%X`  
 현재 로캘의 시간 표현  
  
 `%y`  
 두 자리 숫자 연도 년 (00-99)  
  
 `%Y`  
 세기 포함 10진수 연도  
  
 `%z, %Z`  
 레지스트리 설정에 따라 표준 시간대 이름 또는 표준 시간대 약어(표준 시간대를 알 수 없는 경우 문자 없음)  
  
 `%%`  
 퍼센트 기호  
  
 `printf` 함수에서와같이 모든 서식 코드에는 `#` 플래그가 접두사로 추가될 수 있습니다. 이 경우의 서식 코드 의미는 다음과 같이 변경됩니다.  
  
|코드 형식|의미|  
|-----------------|-------------|  
|`%#a, %#A, %#b, %#B, %#p, %#X, %#z, %#Z, %#%`|`#` 플래그는 무시됩니다.|  
|`%#c`|현재 로캘에 적합한 긴 날짜 및 시간 표현입니다. 예를 들면 "1995년 3월 14일 화요일 12:41:29"와 같습니다.|  
|`%#x`|현재 로캘에 적합한 긴 날짜 표현입니다. 예를 들면 "1995년 3월 14일 화요일"과 같습니다.|  
|`%#d, %#H, %#I, %#j, %#m, %#M, %#S, %#U, %#w, %#W, %#y, %#Y`|선행 0을 제거합니다(있는 경우).|  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`strftime`|\<time.h>|  
|`wcsftime`|\<time.h> 또는 \<wchar.h>|  
|`_strftime_l`|\<time.h>|  
|`_wcsftime_l`|\<time.h> 또는 \<wchar.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## <a name="example"></a>예  
 [time](../../c-runtime-library/reference/time-time32-time64.md)의 예제를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [로캘](../../c-runtime-library/locale.md)   
 [시간 관리](../../c-runtime-library/time-management.md)   
 [문자열 조작](../../c-runtime-library/string-manipulation-crt.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [strcoll 함수](../../c-runtime-library/strcoll-functions.md)   
 [strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](../../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)