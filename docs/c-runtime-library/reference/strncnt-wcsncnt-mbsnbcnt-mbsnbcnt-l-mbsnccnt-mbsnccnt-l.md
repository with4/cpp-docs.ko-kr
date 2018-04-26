---
title: _strncnt, _wcsncnt, _mbsnbcnt, _mbsnbcnt_l, _mbsnccnt, _mbsnccnt_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _mbsnbcnt_l
- _mbsnccnt
- _wcsncnt
- _strncnt
- _mbsnccnt_l
- _mbsnbcnt
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
- _mbsnbcnt
- wcsncnt
- _tcsnbcnt
- _mbsnccnt
- _ftcsnbcnt
- mbsnbcnt
- strncnt
- mbsnbcnt_l
- mbsnccnt_l
- mbsnccnt
- _strncnt
- _wcsncnt
dev_langs:
- C++
helpviewer_keywords:
- _strncnt function
- _mbsnbcnt function
- _mbsnbcnt_l function
- _mbsnccnt_l function
- mbsnbcnt_l function
- mbsnbcnt function
- tcsnbcnt function
- mbsnccnt_l function
- strncnt function
- _tcsnbcnt function
- mbsnccnt function
- wcsncnt function
- _mbsnccnt function
- _wcsncnt function
ms.assetid: 2a022e9e-a307-4acb-a66b-e56e5357f848
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 37e420754c3e534ec3518d6e4764a5366332fd96
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="strncnt-wcsncnt-mbsnbcnt-mbsnbcntl-mbsnccnt-mbsnccntl"></a>_strncnt, _wcsncnt, _mbsnbcnt, _mbsnbcnt_l, _mbsnccnt, _mbsnccnt_l

지정한 개수 내에서 문자 또는 바이트 수를 반환합니다.

> [!IMPORTANT]
> **_mbsnbcnt**, **_mbsnbcnt_l**, **_mbsnccnt**, 및 **_mbsnccnt_l** 는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
size_t _strncnt(
   const char *str,
   size_t count
);
size_t _wcsncnt(
   const wchar_t *str,
   size_t count
);
size_t _mbsnbcnt(
   const unsigned char *str,
   size_t count
);
size_t _mbsnbcnt_l(
   const unsigned char *str,
   size_t count,
   _locale_t locale
);
size_t _mbsnccnt(
   const unsigned char *str,
   size_t count
);
size_t _mbsnccnt_l(
   const unsigned char *str,
   size_t count,
   _locale_t locale
);

```

### <a name="parameters"></a>매개 변수

*str*<br/>
검사할 문자열입니다.

*count*<br/>
문자 수 또는 바이트를 검사할 수 *str*합니다.

*locale*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>반환 값

**_mbsnbcnt** 및 **_mbsnbcnt_l** 발견 되는 바이트 수를 반환 합니다. 첫 번째 범위에서 *count* 의 멀티 바이트 문자의 *str*합니다. **_mbsnccnt** 및 **_mbsnccnt_l** 문자 수를 반환할 첫 번째 범위에서 *count* 의 바이트 *str*합니다. NULL 문자가 검사 하기 전에 발견 되는 경우 *str* 가 문자를 NULL 문자 앞 또는 바이트 수가 반환 완료 합니다. 경우 *str* 보다 적은 이루어져 *count* 문자 또는 바이트 문자열에 문자 또는 바이트 수가 반환 합니다. 경우 *count* 작으면 0 보다 0을 반환 합니다. 이전 버전에서는 이러한 함수는 형식의 반환 값에 **int** 대신 **size_t**합니다.

**_strncnt** 첫 번째 범위에서 문자 수를 반환 *count* 단일 바이트 문자열의 바이트 *str*합니다. **_wcsncnt** 첫 번째 범위에서 문자 수를 반환 *count* 와이드 문자 문자열의 와이드 문자 *str*합니다.

## <a name="remarks"></a>설명

**_mbsnbcnt** 및 **_mbsnbcnt_l** 발견 되는 바이트 수를 계산 첫 번째 범위에서 *count* 의 멀티 바이트 문자의 *str*합니다. **_mbsnbcnt** 및 **_mbsnbcnt_l** 대체 **mtob** 대신 사용 해야 하 고 **mtob**합니다.

**_mbsnccnt** 및 **_mbsnccnt_l** 문자 수를 계산 첫 번째 범위에서 *count* 의 바이트 *str*합니다. 경우 **_mbsnccnt** 및 **_mbsnccnt_l** 더블 바이트 문자의 두 번째 바이트에 NULL을 발생 하면 첫 번째 바이트는 또한 NULL 것으로 간주 하 고 반환 되는 개수 값에 포함 되지 않습니다. **_mbsnccnt** 및 **_mbsnccnt_l** 대체 **btom** 대신 사용 해야 하 고 **btom**합니다.

경우 *str* 아니거나 null 포인터가 *count* 가 0 이면 이러한 함수에 설명 된 대로 잘못 된 매개 변수 처리기를 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md), **errno** 로 설정 된 **EINVAL**, 함수가 0을 반환 합니다.

출력 값은의 설정에 영향을 **LC_CTYPE** 로캘 범주 설정; 참조 [setlocale](setlocale-wsetlocale.md) 자세한 정보에 대 한 합니다. **_l** 접미사가 없는 이러한 함수 버전은 이 로캘 종속 동작에 현재 로캘을 사용하며, **_l** 접미사가 있는 버전은 전달된 로캘 매개 변수를 대신 사용하는 경우를 제외하고는 동일합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|-------------|--------------------------------------|--------------------|-----------------------|
|**_tcsnbcnt**|**_strncnt**|**_mbsnbcnt**|**_wcsncnt**|
|**_tcsnccnt**|**_strncnt**|**_mbsnbcnt**|N/A|
|**_wcsncnt**|N/A|N/A|**_mbsnbcnt**|
|**_wcsncnt**|N/A|N/A|**_mbsnccnt**|
|N/A|N/A|**_mbsnbcnt_l**|**_mbsnccnt_l**|

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_mbsnbcnt**|\<mbstring.h>|
|**_mbsnbcnt_l**|\<mbstring.h>|
|**_mbsnccnt**|\<mbstring.h>|
|**_mbsnccnt_l**|\<mbstring.h>|
|**_strncnt**|\<tchar.h>|
|**_wcsncnt**|\<tchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_mbsnbcnt.c

#include  <mbstring.h>
#include  <stdio.h>

int main( void )
{
   unsigned char str[] = "This is a multibyte-character string.";
   unsigned int char_count, byte_count;
   char_count = _mbsnccnt( str, 10 );
   byte_count = _mbsnbcnt( str, 10 );
   if ( byte_count - char_count )
      printf( "The first 10 characters contain %d multibyte characters\n", char_count );
   else
      printf( "The first 10 characters are single-byte.\n");
}
```

### <a name="output"></a>출력

```Output
The first 10 characters are single-byte.
```

## <a name="see-also"></a>참고자료

[문자열 조작](../../c-runtime-library/string-manipulation-crt.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbsnbcat, _mbsnbcat_l](mbsnbcat-mbsnbcat-l.md)<br/>
