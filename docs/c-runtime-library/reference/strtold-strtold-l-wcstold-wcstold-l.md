---
title: _strtold_l, strtold wcstold, _wcstold_l | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- wcstold
- strtold
- _strtold_l
- _wcstold_l
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
- _tcstold_l
- _wcstold_l
- _tcstold
- strtold
- _strtold_l
- wcstold
dev_langs:
- C++
ms.assetid: 928c0c9a-bc49-445b-8822-100eb5954115
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1a5018f9245da77fbadb301a8fa45d1f0f7b4117
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32417079"
---
# <a name="strtold-strtoldl-wcstold-wcstoldl"></a>strtold, _strtold_l, wcstold, _wcstold_l

문자열을 long 배정밀도 부동 소수점 값으로 변환합니다.

## <a name="syntax"></a>구문

```C
long double strtold(
   const char *strSource,
   char **endptr
);
long double _strtold_l(
   const char *strSource,
   char **endptr,
   _locale_t locale
);
long double wcstold(
   const wchar_t *strSource,
   wchar_t **endptr
);
long double wcstold_l(
   const wchar_t *strSource,
   wchar_t **endptr,
   _locale_t locale
);
```

### <a name="parameters"></a>매개 변수

*strSource*<br/>
변환할 Null 종료 문자열입니다.

*endptr*<br/>
검색을 중지하는 문자에 대한 포인터입니다.

*locale*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>반환 값

**strtold** 으로 부동 소수점 숫자의 값을 반환는 **긴** **double**, 표현을 오버플로가 인해 경우를 제외 하 고-+/-함수가반환하는경우**HUGE_VALL**합니다. 부호 **HUGE_VALL** 표현할 수 없는 값의 부호와 일치 합니다. **strtold** 변환 작업 없이 수행할 수 있습니다 또는 언더플로가 발생 하는 경우 0을 반환 합니다.

**wcstold** 유사 하 게에 값을 반환 **strtold**합니다. 두 함수에 대 한 **errno** 로 설정 된 **ERANGE** 오버플로 또는 언더플로가 발생 한 경우에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다.

반환 코드에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

## <a name="remarks"></a>설명

각 함수는 입력된 문자열을 변환 *strSource* 에 **긴** **double**합니다. **strtold** 함수 읽기를 중단 *strSource* 숫자의 일환으로 인식할 수 없는 첫 번째 문자에서 합니다. 이 문자는 종료 null 문자일 수 있습니다. 와이드 문자 버전의 **strtold** 은 **wcstold**; 해당 *strSource* 인수는 와이드 문자 문자열입니다. 그 외의 경우에는 이들 함수가 동일하게 동작합니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstold**|**strtold**|**strtold**|**wcstold**|
|**_tcstold_l**|**_strtold_l**|**_strtold_l**|**_wcstold_l**|

**LC_NUMERIC** 현재 로캘 범주 설정에 있는 기 수 문자 인식 결정 *strSource*합니다. 자세한 내용은 [setlocale, _wsetlocale](setlocale-wsetlocale.md)을 참조하세요. 없이 함수는 **_l** 접미사 사용은 현재 로캘; **_strtold_l** 및 **_wcstold_l** 동일 **_strtold** 및 **_wcstold** 로캘을 대신 사용 한다는 점을 제외 하 고 있는지를 전달합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

경우 *endptr* 않습니다 **NULL**, 검색을 중지 하는 문자에 대 한 포인터에서 가리키는 위치에 저장 된 *endptr*합니다. 변환 작업 없이 수행할 수 있으면 (유효 자릿수 없이 발견 된 또는 지정 된 잘못 된 base)의 값 *strSource* 가 가리키는 위치에 저장 된 *endptr*합니다.

**strtold** 예상 *strSource* 다음 형식의 문자열을 가리키도록 합니다.

[*공백*] [*기호*] [*자리*] [. *숫자*] [{**d** &#124; **D** &#124; **e** &#124; **E**} [*기호* ]*자릿수*]

A *공백* ; 무시 되는 공백 및 탭 문자가 포함 될 수 *기호* 는 플러스 (**+**) 또는 빼기 (**-**); 및 *자리* 는 되는 하나 이상의 10 진수 숫자입니다. 기수 문자 앞에 숫자가 없는 경우 기수 문자 뒤에는 숫자가 하나 이상 있어야 합니다. 10진수 뒤에 지수가 올 수 있습니다. 지수는 소개 문자(**d**, **D**, **e** 또는 **E**) 및 부호 있는 정수(선택 사항)로 구성됩니다. 지수 부분과 기수 문자가 모두 없으면 기수 문자는 문자열의 마지막 숫자를 따르는 것으로 간주합니다. 이 형식에 맞지 않는 첫 번째 문자가 발견되면 검색이 중지됩니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**strtold**, **_strtold_l**|\<stdlib.h>|
|**wcstold**, **_wcstold_l**|\<stdlib.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_strtold.c
// Build with: cl /W4 /Tc crt_strtold.c
// This program uses strtold to convert a
// string to a long double-precision value.

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char *string;
   char *stopstring;
   long double x;

   string = "3.1415926535898This stopped it";
   x = strtold(string, &stopstring);
   printf("string = %s\n", string);
   printf("   strtold = %.13Lf\n", x);
   printf("   Stopped scan at: %s\n\n", stopstring);
}
```

```Output
string = 3.1415926535898This stopped it
   strtold = 3.1415926535898
   Stopped scan at: This stopped it

```

## <a name="see-also"></a>참고자료

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[문자열을 숫자 값으로 변환하는 함수](../../c-runtime-library/string-to-numeric-value-functions.md)<br/>
[strtod, _strtod_l, wcstod, _wcstod_l](strtod-strtod-l-wcstod-wcstod-l.md)<br/>
[strtol, wcstol, _strtol_l, _wcstol_l](strtol-wcstol-strtol-l-wcstol-l.md)<br/>
[strtoul, _strtoul_l, wcstoul, _wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[localeconv](localeconv.md)<br/>
[_create_locale, _wcreate_locale](create-locale-wcreate-locale.md)<br/>
[_free_locale](free-locale.md)<br/>
