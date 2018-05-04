---
title: strftime, wcsftime, _strftime_l, _wcsftime_l | Microsoft Docs
ms.custom: ''
ms.date: 03/22/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
- _strftime_l
- _wcsftime_l
dev_langs:
- C++
helpviewer_keywords:
- _strftime_l function
- strftime function
- tcsftime function
- _wcsftime_l function
- wcsftime function
- _tcsftime function
- time strings
ms.assetid: 6330ff20-4729-4c4a-82af-932915d893ea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 573e89b7be9818ac45f70c7c614e3bf7869c95f7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="strftime-wcsftime-strftimel-wcsftimel"></a>strftime, wcsftime, _strftime_l, _wcsftime_l

시간 문자열 서식을 지정합니다.

## <a name="syntax"></a>구문

```C
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

### <a name="parameters"></a>매개 변수

*strDest*<br/>
출력 문자열입니다.

*maxsize*<br/>
크기는 *strDest* 버퍼를 문자 단위로 측정 (**char** 또는 **wchar_t**).

*format*<br/>
형식 컨트롤 문자열입니다.

*timeptr*<br/>
**tm** 데이터 구조입니다.

*locale*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>반환 값

**strftime** 에 배치 하는 문자 수를 반환 *strDest* 및 **wcsftime** 해당 와이드 문자 수를 반환 합니다.

총 수가 종료 null을 포함 하 여 이상 *maxsize*모두 **strftime** 및 **wcsftime** 0과의 내용을 반환  *strDest* 확정적이 지 않습니다.

에 있는 문자의 수 *strDest* 이의 리터럴 문자와 숫자와 동일한 *형식* 에 추가 될 수 있는 모든 문자 뿐 아니라 *형식* 형식 지정 코드를 통해 합니다. 문자열의 종료 null은 반환 값 계산에 포함되지 않습니다.

## <a name="remarks"></a>설명

**strftime** 및 **wcsftime** 함수 형식은 **tm** 시간 값에서 *timeptr* 에 제공 된 따라  *형식* 인수와 저장소 버퍼에 결과 *strDest*합니다. 많아야 *maxsize* 문자가 문자열에 배치 됩니다. 에 대 한 설명은의 필드는 *timeptr* 구조을 참조 [asctime](asctime-wasctime.md)합니다. **wcsftime** 와이드 문자에 해당 **strftime**; 문자열 포인터 인수는 와이드 문자열을 가리킵니다. 그 외의 경우에는 이들 함수가 동일하게 작동합니다.

이 함수는 해당 매개 변수의 유효성을 검사합니다. 경우 *strDest*, *형식*, 또는 *timeptr* 가 null 포인터인 경우는 **tm** 데이터 구조에서 다루는 *timeptr* (예를 들어 시간 또는 날짜 범위를 벗어난 값 포함), 유효 하지 또는 경우에는 *형식* 잘못 된 형식 지정 코드를 포함 하는 문자열, 에설명된대로잘못된매개변수처리기가호출[매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 함수는 0 반환 하 고 집합을 계속 하려면 실행 허용 된 경우 **errno** 를 **EINVAL**합니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsftime**|**strftime**|**strftime**|**wcsftime**|

*형식* 인수 하나 이상의 코드; 다음과 같이 구성 됩니다. **printf**, 형식 지정 코드 앞에 백분율 기호 (**%**). 로 시작 하지 않는 문자 **%** 에 변경 되지 않은 복사 *strDest*합니다. **LC_TIME** 현재 로캘 범주의 출력 서식 지정에 영향을 줍니다. **strftime**합니다. (대 한 자세한 내용은 **LC_TIME**, 참조 [setlocale](setlocale-wsetlocale.md).) **strftime** 및 **wcsftime** 함수를 사용 하 여 현재 설정 로캘 합니다. **_strftime_l** 및 **_wcsftime_l** 로캘을 매개 변수로 사용 하 고 현재 설정 하는 대신를 사용 하 여 있는 점을 제외 하 고 이러한 함수의 버전은 동일 합니다. 로캘 합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

**strftime** 함수는 이러한 형식 지정 코드를 지원 합니다.

|||
|-|-|
|코드|바꾸기 문자열|
|**%a**|약식된 요일 이름을 로캘|
|**%A**|전체 요일 이름을 로캘|
|**%b**|약식된 월 이름을 로캘|
|**%B**|로컬에서 월의 전체 이름|
|**%c**|로캘에 적합한 날짜 및 시간 표현|
|**%C**|연도는 100로 나뉘고 (00−99)는 10 진수 숫자는 정수로 잘립니다.|
|**%d**|(01-31)는 10 진수 숫자 월의 일|
|**%D**|에 해당 **%m/%d/%y**|
|**%e**|한 자리 공백을 옵니다는 10 진수 숫자 (1-31)의 월간 일자|
|**%F**|에 해당 **%Y-m %-%d**|
|**%g**|마지막 두 자리의 10 진수는 ISO 8601 주 기반 연도 (00-99)|
|**%G**|10 진수는 ISO 8601 주 기반 연도|
|**%h**|약식된 월 이름 (해당 하 **%b**)|
|**%H**|24 시간 형식의 시간 (00-23)|
|**%I**|12 시간 형식의 시간 (01-12)|
|**%j**|날짜의 10 진수 숫자 (001-366)|
|**%m**|월 (01-12)는 10 진수 숫자|
|**%M**|10 진수 형식의 분 (00-59)|
|**%n**|줄 바꿈 문자 (**\n**)|
|**%p**|로캘의 오전/오후 합니다. 12시간제 표시기|
|**%r**|로캘 12 시간 형식의 시간|
|**%R**|에 해당 **%h: %M**|
|**%S**|10 진수는 숫자 두 번째 (00-59)|
|**%t**|가로 탭 문자 (**\t**)|
|**%T**|에 해당 **%h:%m: %S**, ISO 8601 시간 형식|
|**%u**|ISO 8601 요일 (1-7; 소수로 월요일 = 1)|
|**%U**|소수로 해당 연도의 주 번호 (00-53), 여기서 첫 번째 일요일은 주 1의 첫 번째 날|
|**%V**|ISO 8601 주 번호는 10 진수 숫자 (00-53)|
|**%w**|소수로 요일 (0-6; 일요일은 0 임)|
|**%W**|소수로 해당 연도의 주 번호 (00-53), 여기서 첫 번째 월요일은 1 주의 첫 번째 날|
|**%x**|로캘의 날짜 표현|
|**%X**|로캘의 시간 표현|
|**%y**|두 자리 숫자 연도 년 (00-99)|
|**%Y**|세기 포함 10진수 연도|
|**%z**|ISO 8601 형식으로 측정 된 UTC에서 오프셋 표준 시간대를 알 수 없는 문자 없음|
|**%Z**|로캘의 표준 시간대 이름 또는 레지스트리 설정에 따라 시간대 약어 표준 시간대를 알 수 없는 문자 없음|
|**%%**|퍼센트 기호|

와 같이 **printf** 함수는 **#** 플래그는 서식 코드 접두사 수 있습니다. 이 경우의 서식 코드 의미는 다음과 같이 변경됩니다.

|코드 형식|의미|
|-----------------|-------------|
|**% #a**, **%#A**, **%#b**, **%#B**, **%#g**, **%#G**, **#h%**, **%#n**, **%#p**, **%#t**, **%#u**, **%#w**, **#X %** , **%#z**, **%#Z**, **%#%**|**#** 플래그는 무시 됩니다.|
|**%#c**|긴 날짜 및 시간 표현 로캘에 적합 합니다. 예를 들면 "1995년 3월 14일 화요일 12:41:29"와 같습니다.|
|**%#x**|적절 한 로캘로 자세한 날짜 표현입니다. 예를 들면 "1995년 3월 14일 화요일"과 같습니다.|
|**%#d**, **%#D**, **%#e**, **%#F**, **%#H**, **% #I**, **#j%**, **%#m**, **%#M**, **%#r**, **%#R**, **%#S**, **#T %** , **%#U**, **%#V**, **%#W**, **%#y**, **#Y %**|앞에 오는 0 또는 공백 (있는 경우)를 제거 합니다.|

생성 된 ISO 8601 주와 연도의 주 기반 **%V**, **%g**, 및 **%G**, 주 1 년 1 월 4 일, 첫 번째는 포함 된 주를 여기서은 월요일에 시작 하는 주 사용 해당 연도의 4 일 이상 포함 된 주입니다. 두 번째 연도의 첫 번째 월요일을 사용 하는 경우 4 번째, 또는 3 한 일의 일부인 이전 연도의 마지막 주입니다. 해당 일에 대 한 **%V** 53, 및 교체 **%g** 및 **%G** 이전 연도의 숫자로 대체 됩니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**strftime**|\<time.h>|
|**wcsftime**|\<time.h> 또는 \<wchar.h>|
|**_strftime_l**|\<time.h>|
|**_wcsftime_l**|\<time.h> 또는 \<wchar.h>|

**_strftime_l** 및 **_wcsftime_l** 함수는 Microsoft 전용입니다. 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[time](time-time32-time64.md)의 예제를 참조하세요.

## <a name="see-also"></a>참고자료

[로캘](../../c-runtime-library/locale.md) <br/>
[시간 관리](../../c-runtime-library/time-management.md) <br/>
[문자열 조작](../../c-runtime-library/string-manipulation-crt.md) <br/>
[localeconv](localeconv.md) <br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md) <br/>
[strcoll 함수](../../c-runtime-library/strcoll-functions.md) <br/>
[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
