---
title: _mbsnbset_s, _mbsnbset_s_l | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _mbsnbset_s_l
- _mbsnbset_s
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
apitype: DLLExport
f1_keywords:
- mbsnbset_s
- _mbsnbset_s_l
- _mbsnbset_s
- mbsnbset_s_l
dev_langs:
- C++
helpviewer_keywords:
- tcsnset_s function
- mbsnbset_s function
- mbsnbset_s_l function
- _mbsnbset_s_l function
- _tcsnset_s_l function
- _mbsnbset_s function
- _tcsnset_s function
- tcsnset_s_l function
ms.assetid: 811f92c9-cc31-4bbd-8017-2d1bfc6fb96f
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d37c7bf59e35a33247ecab3b02c0545f88921ec8
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="mbsnbsets-mbsnbsetsl"></a>_mbsnbset_s, _mbsnbset_s_l

설정 하는 첫 번째 **n** 바이트의 지정 된 문자를 멀티 바이트 문자 문자열입니다. 이러한 버전의 [_mbsnbset, _mbsnbset_l](mbsnbset-mbsnbset-l.md)에는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 포함되어 있습니다.

> [!IMPORTANT]
> 이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
errno_t _mbsnbset_s(
   unsigned char *str,
   size_t size,
   unsigned int c,
   size_t count
);
errno_t _mbsnbset_s_l(
   unsigned char *str,
   size_t size,
   unsigned int c,
   size_t count,
   _locale_t locale
);
template <size_t size>
errno_t _mbsnbset_s(
   unsigned char (&str)[size],
   unsigned int c,
   size_t count
); // C++ only
template <size_t size>
errno_t _mbsnbset_s_l(
   unsigned char (&str)[size],
   unsigned int c,
   size_t count,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>매개 변수

*str*<br/>
변경할 문자열입니다.

*size*<br/>
문자열 버퍼의 크기입니다.

*c*<br/>
단일 바이트나 멀티바이트 문자 설정입니다.

*count*<br/>
설정할 바이트 수입니다.

*locale*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>반환 값

성공하면 0이고, 그렇지 않으면 오류 코드입니다.

## <a name="remarks"></a>설명

**_mbsnbset_s** 및 **_mbsnbset_s_l** 기능 설정, 최대, 첫 번째 *count* 바이트의 *str* 를 *c*. 경우 *개수* 의 길이 보다 크면 *str*, 길이의 *str* 대신 사용 됩니다 *count*합니다. 경우 *c* 는 멀티 바이트 문자가 고 지정 된 마지막 바이트에 전체가 들어 맞지 설정할 수 없습니다 *count*, 마지막 바이트 빈 문자로 채워집니다. **_mbsnbset_s** 및 **_mbsnbset_s_l** 종료를 배치 하지 마십시오의 끝에 null *str*합니다.

**_mbsnbset_s** 및 **_mbsnbset_s_l** 유사 **_mbsnset**설정 것 이라는 점을 제외 하면 *count* 바이트 보다는 *count* 문자 *c*합니다.

경우 *str* 은 **NULL** 또는 *count* 0 이면이 함수에 설명 된 대로 잘못 된 매개 변수 예외를 생성 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md). 실행을 계속 하도록 허용 된 경우 **errno** 로 설정 된 **EINVAL** 함수가 반환 하 고 **NULL**합니다. 또한 경우 *c* 은 유효한 멀티 바이트 문자가 아닙니다 **errno** 로 설정 된 **EINVAL** 공백을 대신 사용 됩니다.

출력 값은의 설정에 영향을 **LC_CTYPE** 로캘 범주 설정; 참조 [setlocale, _wsetlocale](setlocale-wsetlocale.md) 자세한 정보에 대 한 합니다. **_mbsnbset_s** 이 함수의 버전은이 로캘 종속 동작에 대 한 현재 로캘을 사용는 **_mbsnbset_s_l** 버전은 로캘 매개 변수 대신 사용 하 여 동일한는 전달합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

C++에서는 템플릿 오버로드를 통해 이러한 함수를 사용하는 것이 보다 간단해집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으므로 크기 인수를 지정할 필요가 없습니다. 자세한 내용은 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.

이러한 함수의 디버그 버전은 우선 0xFD로 버퍼를 채웁니다. 이 동작을 사용하지 않으려면 [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md)를 사용하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsnset_s**|**_strnset_s**|**_mbsnbset_s**|**_wcsnset_s**|
|**_tcsnset_s_l**|`_strnset_s _l`|**_mbsnbset_s_l**|**_wcsnset_s_l**|

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_mbsnbset_s**|\<mbstring.h>|
|**_mbsnbset_s_l**|\<mbstring.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_mbsnbset_s.c
#include <mbstring.h>
#include <stdio.h>

int main( void )
{
   char string[15] = "This is a test";
   /* Set not more than 4 bytes of string to be *'s */
   printf( "Before: %s\n", string );
   _mbsnbset_s( string, sizeof(string), '*', 4 );
   printf( "After:  %s\n", string );
}
```

## <a name="output"></a>출력

```Output
Before: This is a test
After:  **** is a test
```

## <a name="see-also"></a>참고자료

[문자열 조작](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_mbsnbcat, _mbsnbcat_l](mbsnbcat-mbsnbcat-l.md)<br/>
[_strnset, _strnset_l, _wcsnset, _wcsnset_l, _mbsnset, _mbsnset_l](strnset-strnset-l-wcsnset-wcsnset-l-mbsnset-mbsnset-l.md)<br/>
[_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l](strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)<br/>
