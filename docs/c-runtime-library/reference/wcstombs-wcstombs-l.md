---
title: wcstombs, _wcstombs_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- wcstombs
- _wcstombs_l
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
- wcstombs
- _wcstombs_l
dev_langs:
- C++
helpviewer_keywords:
- _wcstombs_l function
- wcstombs function
- string conversion, wide characters
- wide characters, converting
- wcstombs_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 91234252-9ea1-423a-af99-e9d0ce4a40e3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: facc4855d1e36965eff7af70c5cb48f8fb77d419
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="wcstombs-wcstombsl"></a>wcstombs, _wcstombs_l

와이드 문자의 시퀀스를 멀티바이트 문자의 해당 시퀀스로 변환합니다. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [wcstombs_s, _wcstombs_s_l](wcstombs-s-wcstombs-s-l.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
size_t wcstombs(
   char *mbstr,
   const wchar_t *wcstr,
   size_t count
);
size_t _wcstombs_l(
   char *mbstr,
   const wchar_t *wcstr,
   size_t count,
   _locale_t locale
);
template <size_t size>
size_t wcstombs(
   char (&mbstr)[size],
   const wchar_t *wcstr,
   size_t count
); // C++ only
template <size_t size>
size_t _wcstombs_l(
   char (&mbstr)[size],
   const wchar_t *wcstr,
   size_t count,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>매개 변수

*mbstr*<br/>
멀티바이트 문자 시퀀스의 주소입니다.

*wcstr*<br/>
와이드 문자 시퀀스의 주소입니다.

*count*<br/>
멀티바이트 출력 문자열에 저장할 수 있는 최대 바이트 수입니다.

*locale*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>반환 값

경우 **wcstombs** 성공적으로 멀티 바이트 문자열을 변환 종결 제외 하 고 멀티 바이트 출력 문자열에 쓴 바이트 수를 반환 **NULL** (있는 경우). 경우는 *mbstr* 인수가 **NULL**, **wcstombs** 대상 문자열의 바이트에서 필요한 크기를 반환 합니다. 경우 **wcstombs** 멀티 바이트 문자 변환 될 수 없는 와이드 문자를 만나면 형식으로 캐스팅 하는-1이 반환 **size_t** 설정 **errno** 를 **EILSEQ** .

## <a name="remarks"></a>설명

**wcstombs** 함수가 가리키는 와이드 문자 문자열 변환 *wcstr* 를 해당 멀티 바이트 문자를에서 결과 저장는 *mbstr* 배열입니다. *count* 매개 변수는 멀티 바이트 출력 문자열에 저장할 수 있는 바이트의 최대 수를 나타냅니다 (즉, 크기 *mbstr*). 일반적으로는 와이드 문자열을 변환할 때 필요한 바이트의 수를 알 수 없습니다. 출력 문자열에서 1바이트만 사용하면 되면 되는 와이드 문자도 있고 2바이트를 사용해야 하는 문자도 있습니다. 에 있는 경우 2 바이트 입력된 문자열에서 모든 와이드 문자에 대 한 멀티 바이트 출력 문자열 (와이드 문자를 포함 하 여 **NULL**), 결과에 맞게 보장 됩니다.

경우 **wcstombs** 이전 또는 때 와이드 null 문자 (L'\ \0')에서 발생 *count* 발생을 8 비트 0과 중지로 변환 합니다. 따라서 멀티 바이트 문자 문자열에서 *mbstr* 은 null로 끝나는 경우에 **wcstombs** 와이드 null 문자를 변환 하는 동안 발생 합니다. 시퀀스에서 가리키는 경우 *wcstr* 및 *mbstr* 겹치는 경우의 동작 **wcstombs** 정의 되지 않습니다.

경우는 *mbstr* 인수가 **NULL**, **wcstombs** 대상 문자열의 바이트에서 필요한 크기를 반환 합니다.

**wcstombs** 해당 매개 변수의 유효성을 검사 합니다. 경우 *wcstr* 은 **NULL**, if 또는 *count* 보다 크면 **INT_MAX**의 설명 대로 잘못 된 매개 변수 처리기를 호출 하는이 함수 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 합니다. 함수를 설정 하는 경우 실행을 계속 허용 된, **errno** 를 **EINVAL** 하 고-1을 반환 합니다.

**wcstombs** 모든 로캘 종속 동작에 대 한 현재 로캘을 사용 **_wcstombs_l** 대신 전달 된 로캘을 사용 한다는 점을 제외 하 고는 동일 합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

C++에서 이러한 함수는 보다 최신의 보안 대응 함수를 호출하는 템플릿 오버로드를 갖고 있습니다. 자세한 내용은 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**wcstombs**|\<stdlib.h>|
|**_wcstombs_l**|\<stdlib.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

이 프로그램의 동작을 보여 줍니다.는 **wcstombs** 함수입니다.

```C
// crt_wcstombs.c
// compile with: /W3
// This example demonstrates the use
// of wcstombs, which converts a string
// of wide characters to a string of
// multibyte characters.

#include <stdlib.h>
#include <stdio.h>

#define BUFFER_SIZE 100

int main( void )
{
    size_t  count;
    char    *pMBBuffer = (char *)malloc( BUFFER_SIZE );
    wchar_t *pWCBuffer = L"Hello, world.";

    printf("Convert wide-character string:\n" );

    count = wcstombs(pMBBuffer, pWCBuffer, BUFFER_SIZE ); // C4996
    // Note: wcstombs is deprecated; consider using wcstombs_s instead
    printf("   Characters converted: %u\n",
            count );
    printf("    Multibyte character: %s\n\n",
           pMBBuffer );

    free(pMBBuffer);
}
```

```Output
Convert wide-character string:
   Characters converted: 13
    Multibyte character: Hello, world.
```

## <a name="see-also"></a>참고자료

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
[WideCharToMultiByte](http://msdn.microsoft.com/library/windows/desktop/dd374130)<br/>
