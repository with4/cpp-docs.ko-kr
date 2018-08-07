---
title: wcsrtombs_s | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- wcsrtombs_s
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
- wcsrtombs_s
dev_langs:
- C++
helpviewer_keywords:
- string conversion, wide characters
- wcsrtombs_s function
- wide characters, strings
ms.assetid: 9dccb766-113c-44bb-9b04-07a634dddec8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 94e27965d1660f4c344d0026bbfce8685a935c7a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32417303"
---
# <a name="wcsrtombss"></a>wcsrtombs_s

와이드 문자열을 멀티바이트 문자열 표현으로 변환합니다. [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 기능이 향상된 [wcsrtombs](wcsrtombs.md) 버전입니다.

## <a name="syntax"></a>구문

```C
errno_t wcsrtombs_s(
   size_t *pReturnValue,
   char *mbstr,
   size_t sizeInBytes,
   const wchar_t **wcstr,
   sizeof count,
   mbstate_t *mbstate
);
template <size_t size>
errno_t wcsrtombs_s(
   size_t *pReturnValue,
   char (&mbstr)[size],
   const wchar_t **wcstr,
   sizeof count,
   mbstate_t *mbstate
); // C++ only
```

### <a name="parameters"></a>매개 변수

*pReturnValue*<br/>
변환된 문자 수입니다.

*mbstr*<br/>
결과 변환된 멀티바이트 문자열에 대한 버퍼 주소입니다.

*sizeInBytes*<br/>
바이트의 크기는 *mbstr* 버퍼입니다.

*wcstr*<br/>
변환할 와이드 문자열을 가리킵니다.

*count*<br/>
에 저장 될 바이트의 최대 수는 *mbstr* 버퍼 또는 [_TRUNCATE](../../c-runtime-library/truncate.md)합니다.

*mbstate*<br/>
에 대 한 포인터는 **mbstate_t** 변환 상태 개체입니다.

## <a name="return-value"></a>반환 값

성공시 0, 실패시 오류 코드.

|오류 조건|반환 값 및 **errno**|
|---------------------|------------------------------|
|*mbstr* 은 **NULL** 및 *sizeInBytes* > 0|**EINVAL**|
|*wcstr* 은 **NULL**|**EINVAL**|
|대상 버퍼가 너무 작아서 변환된 된 문자열을 포함할 수 (하지 않는 한 *count* 은 **_TRUNCATE**; 아래 설명 참조)|**ERANGE**|

이러한 조건 중 하나라도 발생하는 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 예외가 호출됩니다. 함수 실행을 계속 허용 된, 메시지가 표시 되 면 오류 코드를 반환 하 고 설정 **errno** 테이블에 표시 된 대로 합니다.

## <a name="remarks"></a>설명

**wcsrtombs_s** 함수가 가리키는 와이드 문자 문자열 변환 *wcstr* 가리키는 버퍼에 저장 된 멀티 바이트 문자에 *mbstr*를 사용 하 여는 에 포함 된 변환 상태 *mbstate*합니다. 이러한 조건 중 하나가 충족될 때까지 변환은 문자마다 계속합니다.

- null 와이드 문자가 있는 경우

- 변환할 수 없는 와이드 문자가 있는 경우

- 에 저장 된 바이트 수는 *mbstr* equals 버퍼링 *count*합니다.

대상 문자열은 항상 null로 끝납니다(오류 발생 시도 포함).

경우 *count* 는 특수 값 [_TRUNCATE](../../c-runtime-library/truncate.md), 다음 **wcsrtombs_s** 만큼 문자열 최대한 변환 하지만 null에 대 한 대상 버퍼에 적합 합니다. 종결자입니다.

경우 **wcsrtombs_s** 소스 문자열을 성공적으로 변환에 null 종결자를 포함 하 여 변환된 된 문자열의 바이트에서 크기를 가져가서  *&#42;pReturnValue* (제공 된  *pReturnValue* 않습니다 **NULL**). 이 경우에는 *mbstr* 인수가 **NULL** 이며 필요한 버퍼 크기를 결정 하는 방법을 제공 합니다. 되는 경우 *mbstr* 은 **NULL**, *count* 는 무시 됩니다.

경우 **wcsrtombs_s** 멀티 바이트 문자 변환 될 수 없는 와이드 문자가 있는 곳-1을 가져가서  *\*pReturnValue*, 대상 버퍼를 빈 문자열로 설정 하는, 설정**errno** 를 **EILSEQ**, 반환 **EILSEQ**합니다.

시퀀스에서 가리키는 경우 *wcstr* 및 *mbstr* 겹치는 경우의 동작 **wcsrtombs_s** 정의 되지 않습니다. **wcsrtombs_s** 현재 로캘의 LC_TYPE 범주가 영향을 받습니다.

> [!IMPORTANT]
> 되도록 *wcstr* 및 *mbstr* 이 겹치지 않을 있는지 *개수* 올바르게 변환할 와이드 문자 수를 반영 합니다.

**wcsrtombs_s** 함수에서와 다른 [wcstombs_s, _wcstombs_s_l](wcstombs-s-wcstombs-s-l.md) 다시 시작할 합니다. 변환 상태에 저장 됩니다 *mbstate* 같거나 다른 다시 시작 가능 함수에 대 한 후속 호출에 대 한 합니다. 다시 시작할 수 있는 함수와 다시 시작할 수 없는 함수를 함께 사용할 때는 결과가 정의되지 않습니다. 예를 들어 응용 프로그램 사용 **wcsrlen** 대신 **wcslen**후속 호출 하는 경우, **wcsrtombs_s** 대신 사용한 **wcstombs_s**.

C++에서는 템플릿 오버로드로 인해 이러한 함수를 사용하는 것이 보다 간단해 집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으며(크기 인수를 지정할 필요가 없어짐), 기존의 비보안 함수를 보다 최신의 보안 대응 함수로 자동으로 바꿀 수 있습니다. 자세한 내용은 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.

## <a name="exceptions"></a>예외

**wcsrtombs_s** 함수는 현재 스레드의 호출 함수는 아니면 다중 스레드로부터 안전 **setlocale** 이 함수를 실행 중일 때와 *mbstate* null입니다.

## <a name="example"></a>예제

```cpp
// crt_wcsrtombs_s.cpp
//
// This code example converts a wide
// character string into a multibyte
// character string.
//

#include <stdio.h>
#include <memory.h>
#include <wchar.h>
#include <errno.h>

#define MB_BUFFER_SIZE 100

void main()
{
    const wchar_t   wcString[] =
                    {L"Every good boy does fine."};
    const wchar_t   *wcsIndirectString = wcString;
    char            mbString[MB_BUFFER_SIZE];
    size_t          countConverted;
    errno_t         err;
    mbstate_t       mbstate;

    // Reset to initial shift state
    ::memset((void*)&mbstate, 0, sizeof(mbstate));

    err = wcsrtombs_s(&countConverted, mbString, MB_BUFFER_SIZE,
                      &wcsIndirectString, MB_BUFFER_SIZE, &mbstate);
    if (err == EILSEQ)
    {
        printf( "An encoding error was detected in the string.\n" );
    }
    else
    {
        printf( "The string was successfully converted.\n" );
    }
}
```

```Output
The string was successfully converted.
```

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**wcsrtombs_s**|\<wchar.h>|

## <a name="see-also"></a>참고자료

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[멀티바이트 문자 시퀀스 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[wcrtomb](wcrtomb.md)<br/>
[wcrtomb_s](wcrtomb-s.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[mbsinit](mbsinit.md)<br/>
