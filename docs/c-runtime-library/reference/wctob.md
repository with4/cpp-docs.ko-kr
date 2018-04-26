---
title: wctob | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- wctob
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
- wctob
dev_langs:
- C++
helpviewer_keywords:
- wide characters, converting
- wctob function
- characters, converting
ms.assetid: 46aec98b-c2f2-4e9d-9d89-7db99ba8a9a6
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6bb45aec4b337a7b0aed1a51c50903ad76d2f916
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="wctob"></a>wctob

와이드 문자가 멀티바이트 문자에 해당하는지 확인하고 해당 멀티바이트 문자 표현을 반환합니다.

## <a name="syntax"></a>구문

```C
int wctob(
   wint_t wchar
);
```

### <a name="parameters"></a>매개 변수

*wchar*<br/>
변환할 값입니다.

## <a name="return-value"></a>반환 값

경우 **wctob** 와이드 문자를 성공적으로 변환 멀티 바이트 문자는 1 바이트를 정확 하 게 하는 경우에 해당 멀티 바이트 문자 표현이 반환 합니다. 경우 **wctob** 발생할 멀티 바이트 문자 또는 멀티 바이트 문자 변환 될 수 없는 와이드 문자는 1 바이트 길이가-1이 반환 정확 하 게 합니다.

## <a name="remarks"></a>설명

**wctob** 함수 변환에 포함 된 와이드 문자 *wchar* 반환 되는로 전달 하 여 해당 멀티 바이트 문자를 **int** 경우 값은 멀티 바이트 문자는 1 바이트를 정확 하 게 합니다.

경우 **wctob** 실패 하 고 해당 멀티 바이트 문자가 발견 되었습니다 함수 설정 **errno** 를 **EILSEQ** 하 고-1을 반환 합니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**wctob**|\<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

이 프로그램의 동작을 보여 줍니다.는 **wcstombs** 함수입니다.

```C
// crt_wctob.c
#include <stdio.h>
#include <wchar.h>

int main( void )
{
    int     bChar = 0;
    wint_t  wChar = 0;

    // Set the corresponding wide character to exactly one byte.
    wChar = (wint_t)'A';

    bChar = wctob( wChar );
    if (bChar == WEOF)
    {
        printf( "No corresponding multibyte character was found.\n");
    }
    else
    {
        printf( "Determined the corresponding multibyte character to"
                " be \"%c\".\n", bChar);
    }
}

```

```Output
Determined the corresponding multibyte character to be "A".
```

## <a name="see-also"></a>참고자료

[데이터 변환](../../c-runtime-library/data-conversion.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
[WideCharToMultiByte](http://msdn.microsoft.com/library/windows/desktop/dd374130)<br/>
