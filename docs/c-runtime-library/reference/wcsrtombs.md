---
title: wcsrtombs | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- wcsrtombs
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
- wcsrtombs
dev_langs:
- C++
helpviewer_keywords:
- wcsrtombs function
- string conversion, wide characters
- wide characters, strings
ms.assetid: a8d21fec-0d36-4085-9d81-9b1c61c7259d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0d2ea0252714803fe8cad48635486d2011275407
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="wcsrtombs"></a>wcsrtombs

와이드 문자열을 멀티바이트 문자열 표현으로 변환합니다. 이 함수의 더 안전한 버전을 사용할 수 있습니다. [wcsrtombs_s](wcsrtombs-s.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
size_t wcsrtombs(
   char *mbstr,
   const wchar_t **wcstr,
   sizeof count,
   mbstate_t *mbstate
);
template <size_t size>
size_t wcsrtombs(
   char (&mbstr)[size],
   const wchar_t **wcstr,
   sizeof count,
   mbstate_t *mbstate
); // C++ only
```

### <a name="parameters"></a>매개 변수

*mbstr*<br/>
변환된 결과 멀티바이트 문자열의 주소 위치입니다.

*wcstr*<br/>
변환할 와이드 문자열의 위치를 간접적으로 가리킵니다.

*count*<br/>
변환할 문자의 수입니다.

*mbstate*<br/>
에 대 한 포인터는 **mbstate_t** 변환 상태 개체입니다.

## <a name="return-value"></a>반환 값

정상적으로 변환된 바이트의 수를 반환합니다. null 종결 null 바이트(있는 경우)는 포함되지 않습니다. 오류가 발생하면 -1을 반환합니다.

## <a name="remarks"></a>설명

**wcsrtombs** 함수 변환에 포함 된 지정 된 변환 상태에서 시작 하는 와이드 문자 문자열 *mbstate*에서 가리키는 간접 값에서 *wcstr*의 주소에 *mbstr*합니다. 변환 될 때까지 각 문자에 대해 계속: 와이드 문자 종료 null을 발생 아닌 해당 문자에 오류가 발생 한 후 또는 다음 문자에 포함 된 제한 초과 하는 경우 *count*합니다. 경우 **wcsrtombs** 이전 또는 때 와이드 null 문자 (L'\ \0')에서 발생 *count* 발생을 8 비트 0과 중지로 변환 합니다.

따라서 멀티 바이트 문자 문자열에서 *mbstr* 은 null로 끝나는 경우에 **wcsrtombs** 와이드 null 문자를 변환 하는 동안 발생 합니다. 시퀀스에서 가리키는 경우 *wcstr* 및 *mbstr* 겹치는 경우의 동작 **wcsrtombs** 정의 되지 않습니다. **wcsrtombs** 현재 로캘의 LC_TYPE 범주가 영향을 받습니다.

**wcsrtombs** 함수에서와 다른 [wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md) 다시 시작할 합니다. 변환 상태에 저장 됩니다 *mbstate* 같거나 다른 다시 시작 가능 함수에 대 한 후속 호출에 대 한 합니다. 다시 시작할 수 있는 함수와 다시 시작할 수 없는 함수를 함께 사용할 때는 결과가 정의되지 않습니다.  예를 들어 응용 프로그램 사용 **wcsrlen** 대신 **wcsnlen**후속 호출 하는 경우, **wcsrtombs** 대신 사용한 **wcstombs**.

경우는 *mbstr* 인수가 **NULL**, **wcsrtombs** 대상 문자열의 바이트에서 필요한 크기를 반환 합니다. 경우 *mbstate* 매개 변수가 null 이면 내부 **mbstate_t** 변환 상태를 사용 합니다. 경우 문자 시퀀스 *wchar* 해당 멀티 바이트 없는 문자 표현이-1 반환 및 **errno** 로 설정 되어 **EILSEQ**합니다.

C++에서 이 함수는 해당 최신 보안 버전을 호출하는 템플릿 오버로드를 포함합니다. 자세한 내용은 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.

## <a name="exceptions"></a>예외

**wcsrtombs** 함수는 현재 스레드의 호출 함수는 아니면 다중 스레드로부터 안전 **setlocale** 이 함수를 실행 중일 때 및 *mbstate* null입니다.

## <a name="example"></a>예제

```cpp
// crt_wcsrtombs.cpp
// compile with: /W3
// This code example converts a wide
// character string into a multibyte
// character string.

#include <stdio.h>
#include <memory.h>
#include <wchar.h>
#include <errno.h>

#define MB_BUFFER_SIZE 100

int main()
{
    const wchar_t   wcString[] =
                    {L"Every good boy does fine."};
    const wchar_t   *wcsIndirectString = wcString;
    char            mbString[MB_BUFFER_SIZE];
    size_t          countConverted;
    mbstate_t       mbstate;

    // Reset to initial shift state
    ::memset((void*)&mbstate, 0, sizeof(mbstate));

    countConverted = wcsrtombs(mbString, &wcsIndirectString,
                               MB_BUFFER_SIZE, &mbstate); // C4996
    // Note: wcsrtombs is deprecated; consider using wcsrtombs_s
    if (errno == EILSEQ)
    {
        printf( "An encoding error was detected in the string.\n" );
    }
    else
    {
        printf( "The string was successfuly converted.\n" );
    }
}
```

```Output
The string was successfuly converted.
```

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**wcsrtombs**|\<wchar.h>|

## <a name="see-also"></a>참고자료

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[wcrtomb](wcrtomb.md)<br/>
[wcrtomb_s](wcrtomb-s.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[mbsinit](mbsinit.md)<br/>
