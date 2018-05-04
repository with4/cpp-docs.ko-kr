---
title: strtoumax, _strtoumax_l, wcstoumax, _wcstoumax_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wcstoumax_l
- _strtoumax_l
- wcstoumax
- strtoumax
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- wcstoumax
- _tcstoumax
- _strtoumax_l
- _wcstoumax_l
- _tcstoumax_l
- strtoumax
dev_langs:
- C++
helpviewer_keywords:
- _strtoumax_l function
- conversion functions
- wcstoumax function
- _wcstoumax_l function
- strtoumax function
ms.assetid: 566769f9-495b-4508-b9c6-02217a578897
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0691e26387f70e80718d8af84ba9ff18ad7fd489
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="strtoumax-strtoumaxl-wcstoumax-wcstoumaxl"></a>strtoumax, _strtoumax_l, wcstoumax, _wcstoumax_l

문자열을 지원되는 가장 큰 부호 없는 정수 형식의 정수값으로 변환합니다.

## <a name="syntax"></a>구문

```C
uintmax_t strtoumax(
   const char *strSource,
   char **endptr,
   int base
);
uintmax_t _strtoumax_l(
   const char *strSource,
   char **endptr,
   int base,
   _locale_t locale
);
uintmax_t wcstoumax(
   const wchar_t *strSource,
   wchar_t **endptr,
   int base
);
uintmax_t _wcstoumax_l(
   const wchar_t *strSource,
   wchar_t **endptr,
   int base,
   _locale_t locale
);
```

### <a name="parameters"></a>매개 변수

*strSource*<br/>
변환할 Null 종료 문자열입니다.

*endptr*<br/>
검색을 중지하는 문자에 대한 포인터입니다.

*base*<br/>
사용할 기수입니다.

*locale*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>반환 값

**strtoumax** 있는 경우 변환 된 값을 반환 하거나 **UINTMAX_MAX** 오버플로가 발생 합니다. **strtoumax** 변환 작업 없이 수행할 수 있으면 0을 반환 합니다. **wcstoumax** 유사 하 게에 값을 반환 **strtoumax**합니다. 두 함수에 대 한 **errno** 로 설정 된 **ERANGE** 오버플로 또는 언더플로가 발생 하는 경우.

반환 코드에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

## <a name="remarks"></a>설명

이러한 각 함수는 입력된 문자열을 변환 *strSource* 에 **uintmax_t** 정수 값입니다.

**strtoumax** 읽기를 중단 *strSource* 숫자의 일환으로 인식할 수 없는 첫 번째 문자에서 합니다. Null 종결 문자 수 또는 것이 보다 크거나 같지 않은 첫 번째 숫자 문자 *기본*합니다. **LC_NUMERIC** 로캘 범주 설정에 내의 기 수 문자 인식 여부 결정 *strSource*합니다. 자세한 내용은 [setlocale, _wsetlocale](setlocale-wsetlocale.md)을 참조하세요. **strtoumax** 및 **wcstoumax** ; 현재 로캘을 사용 **_strtoumax_l** 및 **_wcstoumax_l** 는 전달 되는 로캘을 대신 사용 한다는 점을 제외 하 고는 동일 합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

경우 *endptr* 않습니다 **NULL**, 검색을 중지 하는 문자에 대 한 포인터에서 가리키는 위치에 저장 된 *endptr*합니다. 변환 작업 없이 수행할 수 있으면 (유효 자릿수 없이 발견 된 또는 지정 된 잘못 된 base)의 값 *strSource* 가 가리키는 위치에 저장 된 *endptr*합니다.

와이드 문자 버전의 **strtoumax** 은 **wcstoumax**; 해당 *strSource* 인수는 와이드 문자 문자열입니다. 그 외의 경우에는 이들 함수가 동일하게 동작합니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstoumax**|**strtoumax**|**strtoumax**|**wcstoumax**|
|**_tcstoumax_l**|**strtoumax_l**|**_strtoumax_l**|**_wcstoumax_l**|

**strtoumax** 예상 *strSource* 다음 형식의 문자열을 가리키도록 합니다.

> [*공백*] [{**+** &#124; **-**}] [**0** [{ **x** &#124; **X** }]] [*자리* &#124; *문자*]  

A *공백* 공백 및 탭 문자가 무시 되는 구성 될 수 있습니다. *자릿수* 는 되는 하나 이상의 10 진수 숫자입니다. *문자* 가 문자 하나 이상의 'a'-'z' (또는 'A'-'Z'). 이 형식에 맞지 않는 첫 번째 문자가 발견되면 검색이 중지됩니다. 경우 *기본* 은 2와 36 사이의 수의 기반으로 사용 됩니다. 경우 *기본* 은 0으로,이 가리키는 문자열의 초기 문자 *strSource* 기본 결정 하는 데 사용 됩니다. 첫 번째 문자가 '0'이고 두 번째 문자가 'x' 또는 'X'가 아니면 문자열은 8진수 정수로 해석됩니다. 첫 번째 문자가 '0'이고 두 번째 문자가 'x' 또는 'X'이면 문자열은 16진수 정수로 해석됩니다. 첫 번째 문자가 '1'~'9' 이면 문자열은 10진수 정수로 해석됩니다. 문자 'a'~'z' 또는 'A'~'Z'에는 값 10~35가 할당됩니다. 할당된 값이 *밑*보다 작은 문자만 사용할 수 있습니다. 밑의 범위를 벗어난 첫 번째 문자가 발견되면 검색이 중지됩니다. 예를 들어 경우 *기본* 0의 검색 된 첫 번째 문자는 '0', 8 진수 정수 가정 및 '8' 또는 '9' 문자는 검사를 중지 합니다. **strtoumax** 더하기 기호를 사용 하면 (**+**) 또는 빼기 기호 (**-**) 접두사; 앞에 오는 반환 값의 2의 보수 임을 나타낼는 변환된 된 문자열의 절대 값입니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**strtoumax**|\<stdlib.h>|
|**wcstoumax**|\<stdlib.h> 또는 \<wchar.h>|
|**_strtoumax_l**|\<stdlib.h>|
|**_wcstoumax_l**|\<stdlib.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[strtod](strtod-strtod-l-wcstod-wcstod-l.md)의 예제를 참조하세요.

## <a name="see-also"></a>참고자료

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[localeconv](localeconv.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[문자열을 숫자 값으로 변환하는 함수](../../c-runtime-library/string-to-numeric-value-functions.md)<br/>
[strtod, _strtod_l, wcstod, _wcstod_l](strtod-strtod-l-wcstod-wcstod-l.md)<br/>
[strtoimax, _strtoimax_l, wcstoimax, _wcstoimax_l](strtoimax-strtoimax-l-wcstoimax-wcstoimax-l.md)<br/>
[strtol, wcstol, _strtol_l, _wcstol_l](strtol-wcstol-strtol-l-wcstol-l.md)<br/>
[strtoul, _strtoul_l, wcstoul, _wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)<br/>
[strtoll, _strtoll_l, wcstoll, _wcstoll_l](strtoll-strtoll-l-wcstoll-wcstoll-l.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
