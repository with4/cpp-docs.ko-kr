---
title: strpbrk, wcspbrk, _mbspbrk, _mbspbrk_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _mbspbrk
- wcspbrk
- _mbspbrk_l
- strpbrk
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _fstrpbrk
- _mbspbrk
- strpbrk
- _tcspbrk
- _ftcspbrk
- wcspbrk
dev_langs:
- C++
helpviewer_keywords:
- fstrpbrk function
- _ftcspbrk function
- _mbspbrk_l function
- strpbrk function
- _fstrpbrk function
- mbspbrk function
- characters [C++], scanning strings
- _tcspbrk function
- wcspbrk function
- ftcspbrk function
- character sets [C++], scanning strings for characters
- strings [C++], scanning
- tcspbrk function
- _mbspbrk function
- mbspbrk_l function
ms.assetid: 80b504f7-a167-4dde-97ad-4ae3000dc810
caps.latest.revision: 30
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b8cbcd53b46ec99fb81cb962a788c61107373fcf
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="strpbrk-wcspbrk-mbspbrk-mbspbrkl"></a>strpbrk, wcspbrk, _mbspbrk, _mbspbrk_l

문자열에서 지정된 문자 집합의 문자를 검색합니다.

> [!IMPORTANT]
> **_mbspbrk** 및 **_mbspbrk_l** 는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
char *strpbrk(
   const char *str,
   const char *strCharSet
); // C only
char *strpbrk(
   char *str,
   const char *strCharSet
); // C++ only
const char *strpbrk(
   const char *str,
   const char *strCharSet
); // C++ only
wchar_t *wcspbrk(
   const wchar_t *str,
   const wchar_t *strCharSet
); // C only
wchar_t *wcspbrk(
   wchar_t *str,
   const wchar_t *strCharSet
); // C++ only
const wchar_t *wcspbrk(
   const wchar_t *str,
   const wchar_t *strCharSet
); // C++ only
unsigned char *_mbspbrk(
   const unsigned char *str,
   const unsigned char *strCharSet
); // C only
unsigned char *_mbspbrk(
   unsigned char *str,
   const unsigned char *strCharSet
); // C++ only
const unsigned char *_mbspbrk(
   const unsigned char *str,
   const unsigned char *strCharSet
); // C++ only
unsigned char *_mbspbrk_l(
   const unsigned char *str,
   const unsigned char *strCharSet,
   _locale_t locale
); // C only
unsigned char *_mbspbrk_l(
   unsigned char *str,
   const unsigned char *strCharSet,
   _locale_t locale
); // C++ only
const unsigned char *_mbspbrk_l(
   const unsigned char *str,
   const unsigned char* strCharSet,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>매개 변수

*str*<br/>
Null로 종료되는 검색 대상 문자열입니다.

*strCharSet*<br/>
Null 종료 문자 집합입니다.

*locale*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>반환 값

첫 번째 문자를 앞에 대 한 포인터를 반환 *strCharSet* 에 *str*, 또는 **NULL** 포인터 두 문자열 인수 서로 공통 문자가 없는 경우.

## <a name="remarks"></a>설명

**strpbrk** 함수는 첫 번째 앞에 문자에 대 한 포인터를 반환 *str* 의 문자 집합에 속하는 *strCharSet*합니다. 종료 null 문자는 검색에 포함되지 않습니다.

**wcspbrk** 및 **_mbspbrk** 와이드 문자 및 멀티 바이트 문자 버전의 **strpbrk**합니다. 인수 및 반환 값이 **wcspbrk** 은 와이드 문자열이 고 **_mbspbrk** 는 멀티 바이트 문자 문자열입니다.

**_mbspbrk** 해당 매개 변수의 유효성을 검사 합니다. 경우 *str* 또는 *strCharSet* 은 **NULL**에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 실행을 계속 하도록 허용 된 경우 **_mbspbrk** 반환 **NULL** 설정 **errno** 를 **EINVAL**합니다. **strpbrk** 및 **wcspbrk** 매개 변수를 확인 하지 않습니다. 그렇지 않으면 이들 세 함수는 동일하게 작동합니다.

**_mbspbrk** 비슷합니다 **_mbscspn** 점을 제외 하 고 **_mbspbrk** 형식의 값이 아닌 포인터를 반환 [size_t](../../c-runtime-library/standard-types.md)합니다.

C에서 이러한 함수는 사용 된 * * const * * 첫 번째 인수에 대 한 포인터입니다. C++에서는 두 오버로드를 모두 사용할 수 있습니다. 에 대 한 포인터를 수행 하는 오버 로드 * * const * *에 대 한 포인터를 반환 **const **;에 대 한 포인터를 사용 하는 비-하는 버전**const * *에 대 한 포인터를 반환 하는 비-** const **합니다. 매크로 **_CRT_CONST_CORRECT_OVERLOADS** 모두 정의 된는 **const * * 및 비-** const * * 이러한 함수의 버전을 사용할 수 있습니다. 필요 하면 비**const * * 기호를 정의 하는 두 c + + 오버 로드에 대 한 동작 **_CONST_RETURN**합니다.

출력 값은의 설정에 영향을 **LC_CTYPE** 범주 참조 로캘의 자세한 정보에 대 한 설정을 [setlocale](setlocale-wsetlocale.md)합니다. 없는 이러한 함수 버전은 **_l** 이 로캘 종속 동작에 대 한 현재 로캘 사용 접미사; 하 여 버전으로는 **_l** 로캘 매개 변수를 사용 하 여 접미사는 동일 대신에 전달 합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcspbrk**|**strpbrk**|**_mbspbrk**|**wcspbrk**|
|**n/a**|**n/a**|**_mbspbrk_l**|**n/a**|

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**strpbrk**|\<string.h>|
|**wcspbrk**|\<string.h> 또는 \<wchar.h>|
|**_mbspbrk**, **_mbspbrk_l**|\<mbstring.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_strpbrk.c

#include <string.h>
#include <stdio.h>

int main( void )
{
   char string[100] = "The 3 men and 2 boys ate 5 pigs\n";
   char *result = NULL;

   // Return pointer to first digit in "string".
   printf( "1: %s\n", string );
   result = strpbrk( string, "0123456789" );
   printf( "2: %s\n", result++ );
   result = strpbrk( result, "0123456789" );
   printf( "3: %s\n", result++ );
   result = strpbrk( result, "0123456789" );
   printf( "4: %s\n", result );
}
```

```Output
1: The 3 men and 2 boys ate 5 pigs

2: 3 men and 2 boys ate 5 pigs

3: 2 boys ate 5 pigs

4: 5 pigs
```

## <a name="see-also"></a>참고자료

[문자열 조작](../../c-runtime-library/string-manipulation-crt.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strcspn, wcscspn, _mbscspn, _mbscspn_l](strcspn-wcscspn-mbscspn-mbscspn-l.md)<br/>
[strchr, wcschr, _mbschr, _mbschr_l](strchr-wcschr-mbschr-mbschr-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
