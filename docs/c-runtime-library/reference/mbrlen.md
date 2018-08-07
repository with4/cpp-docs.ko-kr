---
title: mbrlen | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- mbrlen
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- mbrlen
dev_langs:
- C++
helpviewer_keywords:
- mbrlen function
ms.assetid: dde8dee9-e091-4c4c-81b3-639808885ae1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 77e5cb106a971bcaf02662bfd8459267a134173a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32404443"
---
# <a name="mbrlen"></a>mbrlen

현재 로캘에서 멀티바이트 문자열을 완성하는 데 필요한 바이트 수를 결정합니다. 이때 멀티바이트 문자의 중간에서 다시 시작할 수 있습니다.

## <a name="syntax"></a>구문

```C
size_t mbrlen(
   const char * str,
   size_t count,
   mbstate_t * mbstate
);
```

### <a name="parameters"></a>매개 변수

*str*<br/>
멀티바이트 문자열에서 검사할 다음 바이트에 대한 포인터입니다.

*count*<br/>
검사할 최대 바이트 수입니다.

*mbstate*<br/>
초기 바이트의 현재 이동 상태에 대 한 포인터 *str*합니다.

## <a name="return-value"></a>반환 값

다음 값 중 하나입니다.

|||
|-|-|
0|다음 *count* 개 이하의 바이트가 와이드 null 문자를 나타내는 멀티 바이트 문자를 완성 합니다.
1 ~ *count*(포함)|다음 *count* 개 이하의 바이트가 올바른 멀티 바이트 문자를 완성 합니다. 반환되는 값은 멀티바이트 문자를 완성하는 바이트 수입니다.
(size_t)(-2)|다음 *count* 바이트가 불완전 하지만 올바를 가능성이 있는 멀티 바이트 문자 및 모든 *count* 바이트를 처리 합니다.
(size_t)(-1)|인코딩 오류가 발생했습니다. 다음 *count* 또는 이하의 바이트가 완전 하며 올바른 멀티 바이트 문자에 기여 하지 않습니다. 이 경우 **errno** EILSEQ로 설정 되며에서 변환 상태가 설정 되어 *mbstate* 지정 되지 않았습니다.

## <a name="remarks"></a>설명

**mbrlen** 함수 검사 최대 *count* 가리키는 바이트부터 바이트 *str* 다음을 완료 하는 데 필요한 바이트 수를 확인 하려면 멀티 바이트 문자를 이동 시퀀스 포함 합니다. 호출 하는 것과 같습니다 `mbrtowc(NULL, str, count, &mbstate)` 여기서 *mbstate* 중 하나는 사용자 제공은 **mbstate_t** 개체 또는 라이브러리에서 제공 하는 정적 내부 개체입니다.

**mbrlen** 저장 하 고에서 불완전 한 멀티 바이트 문자의 이동 상태를 사용 하는 함수는 *mbstate* 매개 변수입니다. 이렇게 하면 **mbrlen** 최대 검사 하는 경우 멀티 바이트 문자의 중간에서 변환을 다시 시작할 수 있어야 *count* 바이트입니다. 경우 *mbstate* null 포인터가 **mbrlen** 은 내부 정적을 사용 하 여 **mbstate_t** 이동 상태를 저장할 개체입니다. 때문에 내부 **mbstate_t** 개체는 스레드로부터 안전 하지, 항상 할당 해 서 사용자 고유의 전달 권장 *mbstate* 매개 변수입니다.

**mbrlen** 함수에서와 다른 [_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md) 다시 시작할 합니다. 이동 상태에 저장 됩니다 *mbstate* 같거나 다른 다시 시작 가능 함수에 대 한 후속 호출에 대 한 합니다. 다시 시작할 수 있는 함수와 다시 시작할 수 없는 함수를 함께 사용할 때는 결과가 정의되지 않습니다.  예를 들어, 응용 프로그램 사용 해야 **wcsrlen** 대신 **wcslen** 후속 호출 하는 경우 **wcsrtombs** 대신 사용 됩니다 **wcstombs**.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|적용할 수 없음|적용할 수 없음|**mbrlen**|적용할 수 없음|

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**mbrlen**|\<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

멀티 바이트 문자 해석이 현재 코드 페이지에 따라 달라 집니다 방법과 다시 시작 기능을 보여 주며 보여 주는이 예제 **mbrlen**합니다.

```C
// crt_mbrlen.c
// Compile by using: cl crt_mbrlen.c
#include <stdlib.h>
#include <stdio.h>
#include <string.h>
#include <locale.h>
#include <wchar.h>

size_t Example(const char * pStr)
{
    size_t      charLen = 0;
    size_t      charCount = 0;
    mbstate_t   mbState = {0};

    while ((charLen = mbrlen(pStr++, 1, &mbState)) != 0 &&
            charLen != (size_t)-1)
    {
        if (charLen != (size_t)-2) // if complete mbcs char,
        {
            charCount++;
        }
    }
    return (charCount);
}

int main( void )
{
    int         cp;
    size_t      charCount = 0;
    const char  *pSample =
        "\x82\xD0\x82\xE7\x82\xAA\x82\xC8: Shift-jis hiragana.";

    cp = _getmbcp();
    charCount = Example(pSample);
    printf("\nCode page: %d\n%s\nCharacter count: %d\n",
        cp, pSample, charCount);

    setlocale(LC_ALL, "ja-JP"); // Set Japanese locale
    _setmbcp(932); // and Japanese multibyte code page
    cp = _getmbcp();
    charCount = Example(pSample);
    printf("\nCode page: %d\n%s\nCharacter count: %d\n",
        cp, pSample, charCount);
}
```

```Output

Code page: 0
é╨éτé¬é╚: Shift-jis hiragana.
Character count: 29

Code page: 932
????: Shift-jis hiragana.
Character count: 25

```

## <a name="see-also"></a>참고자료

[문자열 조작](../../c-runtime-library/string-manipulation-crt.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
