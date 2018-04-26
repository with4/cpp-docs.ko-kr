---
title: wcstombs_s, _wcstombs_s_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _wcstombs_s_l
- wcstombs_s
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
- wcstombs_s
- _wcstombs_s_l
dev_langs:
- C++
helpviewer_keywords:
- wcstombs_s function
- string conversion, wide characters
- wide characters, converting
- _wcstombs_s_l function
- wcstombs_s_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 105f2d33-221a-4f6d-864c-23c1865c42af
caps.latest.revision: 31
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d392e2a970627cd59d4cb96ae354c3b15406731e
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="wcstombss-wcstombssl"></a>wcstombs_s, _wcstombs_s_l

와이드 문자의 시퀀스를 멀티바이트 문자의 해당 시퀀스로 변환합니다. [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 기능이 향상된 [wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md) 버전입니다.

## <a name="syntax"></a>구문

```C
errno_t wcstombs_s(
   size_t *pReturnValue,
   char *mbstr,
   size_t sizeInBytes,
   const wchar_t *wcstr,
   size_t count
);

errno_t _wcstombs_s_l(
   size_t *pReturnValue,
   char *mbstr,
   size_t sizeInBytes,
   const wchar_t *wcstr,
   size_t count,
   _locale_t locale
);

template <size_t size>
errno_t wcstombs_s(
   size_t *pReturnValue,
   char (&mbstr)[size],
   const wchar_t *wcstr,
   size_t count
); // C++ only

template <size_t size>
errno_t _wcstombs_s_l(
   size_t *pReturnValue,
   char (&mbstr)[size],
   const wchar_t *wcstr,
   size_t count,
   _locale_t locale
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
에 저장 하는 바이트의 최대 수는 *mbstr* 버퍼에 null 종결 문자를 제외 또는 [_TRUNCATE](../../c-runtime-library/truncate.md)합니다.

*locale*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>반환 값

성공시 0, 실패시 오류 코드.

|오류 조건|반환 값 및 **errno**|
|---------------------|------------------------------|
|*mbstr* 은 **NULL** 및 *sizeInBytes* > 0|**EINVAL**|
|*wcstr* 은 **NULL**|**EINVAL**|
|대상 버퍼가 너무 작아서 변환된 된 문자열을 포함할 수 (하지 않는 한 *count* 은 **_TRUNCATE**; 아래 설명 참조)|**ERANGE**|

이러한 조건 중 하나라도 발생하는 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 예외가 호출됩니다. 함수 실행을 계속 허용 된, 메시지가 표시 되 면 오류 코드를 반환 하 고 설정 **errno** 테이블에 표시 된 대로 합니다.

## <a name="remarks"></a>설명

**wcstombs_s** 함수가 가리키는 와이드 문자 문자열 변환 *wcstr* 가리키는 버퍼에 저장 된 멀티 바이트 문자에 *mbstr*합니다. 이러한 조건 중 하나가 충족될 때까지 변환은 문자마다 계속합니다.

- null 와이드 문자가 있는 경우

- 변환할 수 없는 와이드 문자가 있는 경우

- 에 저장 된 바이트 수는 *mbstr* equals 버퍼링 *count*합니다.

대상 문자열은 항상 null로 끝납니다(오류 발생 시도 포함).

경우 *count* 는 특수 값 [_TRUNCATE](../../c-runtime-library/truncate.md), 다음 **wcstombs_s** 만큼 문자열 최대한 변환 하지만 null에 대 한 대상 버퍼에 적합 합니다. 종결자입니다. 반환 값은 문자열이 잘리는 경우 **STRUNCATE**는 변환이 성공한 것으로 간주 됩니다.

경우 **wcstombs_s** 소스 문자열을 성공적으로 변환에 null 종결자를 포함 하 여 변환된 된 문자열의 바이트에서 크기를 가져가서  *&#42;pReturnValue* (제공 된  *pReturnValue* 않습니다 **NULL**). 이 경우에는 *mbstr* 인수가 **NULL** 이며 필요한 버퍼 크기를 결정 하는 방법을 제공 합니다. 되는 경우 *mbstr* 은 **NULL**, *count* 는 무시 됩니다.

경우 **wcstombs_s** 멀티 바이트 문자 변환 될 수 없는 와이드 문자를 만나면 0 가져가서  *&#42;pReturnValue*, 대상 버퍼를 빈 문자열로 설정 하는, 설정 **errno**  를 **EILSEQ**, 반환 **EILSEQ**합니다.

시퀀스에서 가리키는 경우 *wcstr* 및 *mbstr* 겹치는 경우의 동작 **wcstombs_s** 정의 되지 않습니다.

> [!IMPORTANT]
> 되도록 *wcstr* 및 *mbstr* 이 겹치지 않을 있는지 *개수* 올바르게 변환할 와이드 문자 수를 반영 합니다.

**wcstombs_s** 모든 로캘 종속 동작에 대 한 현재 로캘을 사용 **_wcstombs_s_l** 동일 **wcstombs** 대신 전달 된 로캘을 사용 하 여 합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

C++에서는 템플릿 오버로드로 인해 이러한 함수를 사용하는 것이 보다 간단해 집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으며(크기 인수를 지정할 필요가 없어짐), 기존의 비보안 함수를 보다 최신의 보안 대응 함수로 자동으로 바꿀 수 있습니다. 자세한 내용은 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)을 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**wcstombs_s**|\<stdlib.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

이 프로그램의 동작을 보여 줍니다.는 **wcstombs_s** 함수입니다.

```C
// crt_wcstombs_s.c
// This example converts a wide character
// string to a multibyte character string.
#include <stdio.h>
#include <stdlib.h>
#include <assert.h>

#define BUFFER_SIZE 100

int main( void )
{
    size_t   i;
    char      *pMBBuffer = (char *)malloc( BUFFER_SIZE );
    wchar_t*pWCBuffer = L"Hello, world.";

    printf( "Convert wide-character string:\n" );

    // Conversion
    wcstombs_s(&i, pMBBuffer, (size_t)BUFFER_SIZE,
               pWCBuffer, (size_t)BUFFER_SIZE );

    // Output
    printf("   Characters converted: %u\n", i);
    printf("    Multibyte character: %s\n\n",
     pMBBuffer );

    // Free multibyte character buffer
    if (pMBBuffer)
    {
    free(pMBBuffer);
    }
}
```

```Output
Convert wide-character string:
   Characters converted: 14
    Multibyte character: Hello, world.
```

## <a name="see-also"></a>참고자료

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[wctomb_s, _wctomb_s_l](wctomb-s-wctomb-s-l.md)<br/>
[WideCharToMultiByte](http://msdn.microsoft.com/library/windows/desktop/dd374130)<br/>
