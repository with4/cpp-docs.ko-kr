---
title: strchr, wcschr, _mbschr, _mbschr_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- strchr
- wcschr
- _mbschr_l
- _mbschr
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
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- _ftcschr
- strchr
- wcschr
- _tcschr
- _mbschr
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], searching
- mbschr function
- _ftcschr function
- _mbschr function
- characters [C++], finding in strings
- _mbschr_l function
- ftcschr function
- wcschr function
- strchr function
- _tcschr function
- tcschr function
- mbschr_l function
ms.assetid: 2639905d-e983-43b7-b885-abef32cfac43
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6d83407efee1da2bc1c59cf0d869f54f6022a4eb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="strchr-wcschr-mbschr-mbschrl"></a>strchr, wcschr, _mbschr, _mbschr_l
현재 로캘 또는 지정된 LC_CTYPE 변환 상태 범주를 사용하여 문자열에서 문자를 찾습니다.

> [!IMPORTANT]
> **_mbschr** 및 **_mbschr_l** 는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
char *strchr(
   const char *str,
   int c
);  // C only
char *strchr(
   char * str,
   int c
); // C++ only
const char *strchr(
   const char * str,
   int c
); // C++ only
wchar_t *wcschr(
   const wchar_t *str,
   wchar_t c
); // C only
wchar_t *wcschr(
   wchar_t *str,
   wchar_t c
);  // C++ only
const wchar_t *wcschr(
   const wchar_t *str,
   wchar_t c
);  // C++ only
unsigned char *_mbschr(
   const unsigned char *str,
   unsigned int c
); // C only
unsigned char *_mbschr(
   unsigned char *str,
   unsigned int c
); // C++ only
const unsigned char *_mbschr(
   const unsigned char *str,
   unsigned int c
); // C++ only
unsigned char *_mbschr_l(
   const unsigned char *str,
   unsigned int c,
   _locale_t locale
); // C only
unsigned char *_mbschr_l(
   unsigned char *str,
   unsigned int c,
   _locale_t locale
); // C++ only
const unsigned char *_mbschr_l(
   const unsigned char *str,
   unsigned int c,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>매개 변수

*str*<br/>
Null 종료 소스 문자열입니다.

*c*<br/>
찾을 문자입니다.

*locale*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>반환 값

첫 번째로 나타나는 항목에 대 한 포인터를 반환 이러한 각 함수 *c* 에 *str*, 또는 **NULL** 경우 *c* 찾을 수 없습니다.

## <a name="remarks"></a>설명

**strchr** 함수 첫 번째로 나타나는 항목을 찾습니다. *c* 에 *str*, 반환 또는 **NULL** 경우 *c* 은 찾을 수 없습니다. null 종료 문자는 검색에 포함됩니다.

**wcschr**, **_mbschr** 및 **_mbschr_l** 와이드 문자 및 멀티 바이트 문자 버전의 **strchr**합니다. 인수 및 반환 값이 **wcschr** 은 와이드 문자열이 고 **_mbschr** 는 멀티 바이트 문자 문자열입니다. **_mbschr** 멀티 바이트 문자 시퀀스를 인식 합니다. 또한 문자열이 null 포인터 인지, **_mbschr** 에 설명 된 대로 잘못 된 매개 변수 처리기를 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 하도록 허용 된 경우 **_mbschr** 반환 **NULL** 설정 **errno** 를 **EINVAL**합니다. **strchr** 및 **wcschr** 매개 변수를 확인 하지 않습니다. 그렇지 않으면 이들 세 함수는 동일하게 작동합니다.

출력 값은의 설정에 영향을 **LC_CTYPE** 범주 참조 로캘의 자세한 정보에 대 한 설정을 [setlocale](setlocale-wsetlocale.md)합니다. **_l** 접미사가 없는 이러한 함수 버전은 이 로캘 종속 동작에 현재 로캘을 사용하며, **_l** 접미사가 있는 버전은 전달된 로캘 매개 변수를 대신 사용하는 경우를 제외하고는 동일합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

C에서 이러한 함수는 사용 된 * * const * * 첫 번째 인수에 대 한 포인터입니다. C++에서는 두 오버로드를 모두 사용할 수 있습니다. 에 대 한 포인터를 수행 하는 오버 로드 * * const * *에 대 한 포인터를 반환 **const **;에 대 한 포인터를 사용 하는 비-하는 버전**const * *에 대 한 포인터를 반환 하는 비-** const **합니다. 매크로 **_CRT_CONST_CORRECT_OVERLOADS** 모두 정의 된는 **const * * 및 비-** const * * 이러한 함수의 버전을 사용할 수 있습니다. 필요 하면 비**const * * 기호를 정의 하는 두 c + + 오버 로드에 대 한 동작 **_CONST_RETURN**합니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcschr**|**strchr**|**_mbschr**|**wcschr**|
|**_n/a**|**n/a**|**_mbschr_l**|**n/a**|

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**strchr**|\<string.h>|
|**wcschr**|\<string.h> 또는 \<wchar.h>|
|**_mbschr**, **_mbschr_l**|\<mbstring.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_strchr.c
//
// This program illustrates searching for a character
// with strchr (search forward) or strrchr (search backward).
//

#include <string.h>
#include <stdio.h>

int  ch = 'r';

char string[] = "The quick brown dog jumps over the lazy fox";
char fmt1[] =   "         1         2         3         4         5";
char fmt2[] =   "12345678901234567890123456789012345678901234567890";

int main( void )
{
   char *pdest;
   int result;

   printf_s( "String to be searched:\n      %s\n", string );
   printf_s( "      %s\n      %s\n\n", fmt1, fmt2 );
   printf_s( "Search char:   %c\n", ch );

   // Search forward.
   pdest = strchr( string, ch );
   result = (int)(pdest - string + 1);
   if ( pdest != NULL )
      printf_s( "Result:   first %c found at position %d\n",
              ch, result );
   else
      printf_s( "Result:   %c not found\n", ch );

   // Search backward.
   pdest = strrchr( string, ch );
   result = (int)(pdest - string + 1);
   if ( pdest != NULL )
      printf_s( "Result:   last %c found at position %d\n", ch, result );
   else
      printf_s( "Result:\t%c not found\n", ch );
}
```

```Output
String to be searched:
      The quick brown dog jumps over the lazy fox
               1         2         3         4         5
      12345678901234567890123456789012345678901234567890

Search char:   r
Result:   first r found at position 12
Result:   last r found at position 30
```

## <a name="see-also"></a>참고자료

[문자열 조작](../../c-runtime-library/string-manipulation-crt.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strcspn, wcscspn, _mbscspn, _mbscspn_l](strcspn-wcscspn-mbscspn-mbscspn-l.md)<br/>
[strncat, _strncat_l, wcsncat, _wcsncat_l, _mbsncat, _mbsncat_l](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l](strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strpbrk, wcspbrk, _mbspbrk, _mbspbrk_l](strpbrk-wcspbrk-mbspbrk-mbspbrk-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[strstr, wcsstr, _mbsstr, _mbsstr_l](strstr-wcsstr-mbsstr-mbsstr-l.md)<br/>
