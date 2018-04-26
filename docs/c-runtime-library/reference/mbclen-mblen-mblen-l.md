---
title: _mbclen, mblen, _mblen_l | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _mbclen
- mblen
- _mblen_l
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
- mblen
- ftclen
- _mbclen
- tclen
- _ftclen
- _tclen
- mbclen
dev_langs:
- C++
helpviewer_keywords:
- tclen function
- _mblen_l function
- _tclen function
- mblen_l function
- _mbclen function
- mbclen function
- mblen function
ms.assetid: d5eb92a0-b7a3-464a-aaf7-9890a8e3ed70
caps.latest.revision: 24
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4f0478d5d6337d185d30a7fee8d012104bdff13d
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="mbclen-mblen-mblenl"></a>_mbclen, mblen, _mblen_l

멀티바이트 문자의 길이를 가져오고 유효성을 확인합니다.

> [!IMPORTANT]
> 이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
size_t _mbclen(
   const unsigned char *c
);
int mblen(
   const char *mbstr,
   size_t count
);
int _mblen_l(
   const char *mbstr,
   size_t count,
   _locale_t locale
);
```

### <a name="parameters"></a>매개 변수

*c*<br/>
멀티바이트 문자입니다.

*mbstr*<br/>
멀티바이트 문자 바이트 시퀀스의 주소입니다.

*count*<br/>
검사할 바이트 수입니다.

*locale*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>반환 값

**_mbclen** 열리는지에 따라 1 또는 2를 반환 멀티 바이트 문자 *c* 1 또는 2 바이트의 길이 바이트입니다. 에 대 한 반환 오류인 **_mbclen**합니다. 경우 *mbstr* 않습니다 **NULL**, **mblen** 멀티 바이트 문자의 바이트의 길이 반환 합니다. 경우 *mbstr* 은 **NULL** 하거나 와이드 null 문자를 가리키는 **mblen** 0을 반환 합니다. 경우 개체는 *mbstr* 가리키는 첫 번째 내에서 유효한 멀티 바이트 문자를 형성 하지 않습니다 *count* 문자인 **mblen** -1을 반환 합니다.

## <a name="remarks"></a>설명

**_mbclen** 멀티 바이트 문자의 바이트에는 길이 반환 하는 함수 *c*합니다. 경우 *c* 암시적으로 호출에 의해 결정 된 멀티 바이트 문자의 선행 바이트를 가리키지 않습니다 **_ismbblead**, 결과인 **_mbclen** 를 예측할 수 없습니다.

**mblen** 바이트의 길이 반환 *mbstr* 유효한 멀티 바이트 문자 이며 코드 페이지와 관련 된 멀티 바이트 문자의 유효성을 확인 하는 경우. **mblen** 검사 *count* 또는에 포함 된 더 적은 바이트 *mbstr*, 최대 **MB_CUR_MAX** 바이트입니다.

출력 값은의 설정에 영향을 **LC_CTYPE** 로캘 범주 설정; 참조 [setlocale](setlocale-wsetlocale.md) 자세한 정보에 대 한 합니다. **_l** 접미사가 없는 이러한 함수 버전은 이 로캘 종속 동작에 현재 로캘을 사용하며, **_l** 접미사가 있는 버전은 전달된 로캘 매개 변수를 대신 사용하는 경우를 제외하고는 동일합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 루틴 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tclen**|매크로 또는 인라인 함수에 매핑|**_mbclen**|매크로 또는 인라인 함수에 매핑|

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_mbclen**|\<mbstring.h>|
|**mblen**|\<stdlib.h>|
|**_mblen_l**|\<stdlib.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_mblen.c
/* illustrates the behavior of the mblen function
*/

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
    int      i;
    char    *pmbc = (char *)malloc( sizeof( char ) );
    wchar_t  wc   = L'a';

    printf( "Convert wide character to multibyte character:\n" );
    wctomb_s( &i, pmbc, sizeof(char), wc );
    printf( "   Characters converted: %u\n", i );
    printf( "   Multibyte character: %x\n\n", *pmbc );

    i = mblen( pmbc, MB_CUR_MAX );
    printf( "Length in bytes of multibyte character %x: %u\n", *pmbc, i );

    pmbc = NULL;
    i = mblen( pmbc, MB_CUR_MAX );
    printf( "Length in bytes of NULL multibyte character %x: %u\n", pmbc, i );
}
```

```Output
Convert wide character to multibyte character:
   Characters converted: 1
   Multibyte character: 61

Length in bytes of multibyte character 61: 1
Length in bytes of NULL multibyte character 0: 0
```

## <a name="see-also"></a>참고자료

[문자 분류](../../c-runtime-library/character-classification.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbccpy, _mbccpy_l](mbccpy-mbccpy-l.md)<br/>
[strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)<br/>
