---
title: strrchr, wcsrchr, _mbsrchr, _mbsrchr_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- strrchr
- wcsrchr
- _mbsrchr
- _mbsrchr_l
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
- ntdll.dll
- ucrtbase.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _tcsrchr
- _ftcsrchr
- strrchr
- wcsrchr
- _mbsrchr
dev_langs:
- C++
helpviewer_keywords:
- _mbsrchr function
- tcsrchr function
- mbsrchr_l function
- characters [C++], scanning for
- ftcsrchr function
- _tcsrchr function
- strings [C++], scanning
- mbsrchr function
- strrchr function
- scanning strings
- wcsrchr function
- _ftcsrchr function
- _mbsrchr_l function
ms.assetid: 75cf2664-758e-49bb-bf6b-8a139cd474d2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a41b52b07d5f3abc290773bd7c96ca82d1b698a8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32416277"
---
# <a name="strrchr-wcsrchr-mbsrchr-mbsrchrl"></a>strrchr, wcsrchr, _mbsrchr, _mbsrchr_l

문자열에서 마지막으로 나오는 문자를 검색합니다.

> [!IMPORTANT]
> **_mbsrchr** 및 **_mbsrchr_l** 는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
char *strrchr(
   const char *str,
   int c
); // C only
char *strrchr(
   char *str,
   int c
); // C++ only
const char *strrchr(
   const char *str,
   int c
); // C++ only
wchar_t *wcsrchr(
   const wchar_t *str,
   wchar_t c
); // C only
wchar_t *wcsrchr(
   wchar_t *str,
   wchar_t c
); // C++ only
const wchar_t *wcsrchr(
   const wchar_t *str,
   wchar_t c
); // C++ only
unsigned char *_mbsrchr(
   const unsigned char *str,
   unsigned int c
); // C only
unsigned char *_mbsrchr(
   unsigned char *str,
   unsigned int c
); // C++ only
const unsigned char *_mbsrchr(
   const unsigned char *str,
   unsigned int c
); // C++ only
unsigned char *_mbsrchr_l(
   const unsigned char *str,
   unsigned int c,
   _locale_t locale
); // C only
unsigned char *_mbsrchr_l(
   unsigned char *str,
   unsigned int c,
   _locale_t locale
); // C++ only
const unsigned char *_mbsrchr_l(
   const unsigned char *str,
   unsigned int c,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>매개 변수

*str*<br/>
검색할 Null 종료 문자열입니다.

*c*<br/>
찾을 문자입니다.

*locale*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>반환 값

마지막으로 나타나는 항목에 대 한 포인터를 반환 *c* 에 *str*, 또는 **NULL** 경우 *c* 찾을 수 없습니다.

## <a name="remarks"></a>설명

**strrchr** 함수 마지막으로 나타나는 항목을 찾습니다. *c* (변환할 **char**)에서 *str*합니다. 검색에는 종료형 null 문자를 포함합니다.

**wcsrchr** 및 **_mbsrchr** 와이드 문자 및 멀티 바이트 문자 버전의 **strrchr**합니다. 인수 및 반환 값이 **wcsrchr** 은 와이드 문자열이 고 **_mbsrchr** 는 멀티 바이트 문자 문자열입니다.

C에서 이러한 함수는 사용 된 * * const * * 첫 번째 인수에 대 한 포인터입니다. C++에서는 두 오버로드를 모두 사용할 수 있습니다. 에 대 한 포인터를 수행 하는 오버 로드 * * const * *에 대 한 포인터를 반환 **const **;에 대 한 포인터를 사용 하는 비-하는 버전**const * *에 대 한 포인터를 반환 하는 비-** const **합니다. 매크로 **_CRT_CONST_CORRECT_OVERLOADS** 모두 정의 된는 **const * * 및 비-** const * * 이러한 함수의 버전을 사용할 수 있습니다. 필요 하면 비**const * * 기호를 정의 하는 두 c + + 오버 로드에 대 한 동작 **_CONST_RETURN**합니다.

**_mbsrchr** 해당 매개 변수의 유효성을 검사 합니다. 경우 *str* 은 **NULL**에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 하도록 허용 된 경우 **errno** 로 설정 된 **EINVAL** 및 **_mbsrchr** 0을 반환 합니다. **strrchr** 및 **wcsrchr** 매개 변수를 확인 하지 않습니다. 그렇지 않으면 이들 세 함수는 동일하게 작동합니다.

출력 값은의 설정에 영향을 **LC_CTYPE** 범주 참조 로캘의 자세한 정보에 대 한 설정을 [setlocale](setlocale-wsetlocale.md)합니다. **_l** 접미사가 없는 이러한 함수 버전은 이 로캘 종속 동작에 현재 로캘을 사용하며, **_l** 접미사가 있는 버전은 전달된 로캘 매개 변수를 대신 사용하는 경우를 제외하고는 동일합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsrchr**|**strrchr**|**_mbsrchr**|**wcsrchr**|
|**n/a**|**n/a**|**_mbsrchr_l**|**n/a**|

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**strrchr**|\<string.h>|
|**wcsrchr**|\<string.h> 또는 \<wchar.h>|
|**_mbsrchr**, **_mbsrchr_l**|\<mbstring.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

사용 하는 예제에 대 한 **strrchr**, 참조 [strchr](strchr-wcschr-mbschr-mbschr-l.md)합니다.

## <a name="see-also"></a>참고자료

[문자열 조작](../../c-runtime-library/string-manipulation-crt.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strchr, wcschr, _mbschr, _mbschr_l](strchr-wcschr-mbschr-mbschr-l.md)<br/>
[strcspn, wcscspn, _mbscspn, _mbscspn_l](strcspn-wcscspn-mbscspn-mbscspn-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strpbrk, wcspbrk, _mbspbrk, _mbspbrk_l](strpbrk-wcspbrk-mbspbrk-mbspbrk-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
