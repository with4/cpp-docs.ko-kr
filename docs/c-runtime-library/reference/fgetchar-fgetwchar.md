---
title: _fgetchar, _fgetwchar | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _fgetchar
- _fgetwchar
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- fgetwchar
- _fgettchar
- _fgetchar
- _fgetwchar
- fgettchar
dev_langs:
- C++
helpviewer_keywords:
- fgetwchar function
- _fgetchar function
- fgettchar function
- _fgetwchar function
- _fgettchar function
- standard input, reading from
- fgetchar function
ms.assetid: 8bce874c-701a-41a3-b1b2-feff266fb5b9
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8b6f6933d8483e3fee792829b0efde8e35ad91a1
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="fgetchar-fgetwchar"></a>_fgetchar, _fgetwchar

문자를 읽고 **stdin**합니다.

## <a name="syntax"></a>구문

```C
int _fgetchar( void );
wint_t _fgetwchar( void );
```

## <a name="return-value"></a>반환 값

**_fgetchar** 으로 읽은 문자를 반환 합니다.는 **int** 하거나 반환할 **EOF** 오류 또는 파일의 끝을 나타냅니다. **_ * * * fgetwchar** 반환로 [wint_t](../../c-runtime-library/standard-types.md), 읽은 문자에 해당 하거나 반환 되는 와이드 문자 **WEOF** 오류 또는 파일의 끝을 나타냅니다. 두 함수에 대 한 사용 **feof** 또는 **ferror** 오류와 파일 끝 조건을 구별할 수 있습니다.

## <a name="remarks"></a>설명

이러한 함수는 단일 문자를 읽습니다 **stdin**합니다. 그러고 나서 다음 문자를 가리킬 연결된 파일 포인터(정의된 경우)를 늘립니다. 스트림이 파일 끝에 있는 경우 스트림에 대한 파일 끝 표시기가 설정됩니다.

**_fgetchar** 같습니다 `fgetc( stdin )`합니다. 입력할 필요는 **getchar**, 하지만 아닌 함수 및 매크로 함수로 구현 합니다. **_fgetwchar** 의 와이드 문자 버전이 **_fgetchar**합니다.

이러한 함수는 ANSI 표준과 호환되지 않습니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_fgettchar**|**_fgetchar**|**_fgetchar**|**_fgetwchar**|

## <a name="requirements"></a>요구 사항

|함수|필수 헤더|
|--------------|---------------------|
|**_fgetchar**|\<stdio.h>|
|**_fgetwchar**|\<stdio.h> 또는 \<wchar.h>|

콘솔 유니버설 Windows 플랫폼 (UWP) 응용 프로그램에서 지원 되지 않습니다. 콘솔에 연결된 된 표준 스트림 핸들-**stdin**, **stdout**, 및 **stderr**-C 런타임 함수 UWP 앱에서 사용할 수 있는 전에 리디렉션되어야 . 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_fgetchar.c
// This program uses _fgetchar to read the first
// 80 input characters (or until the end of input)
// and place them into a string named buffer.
//

#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   char buffer[81];
   int  i, ch;

   // Read in first 80 characters and place them in "buffer":
   ch = _fgetchar();
   for( i=0; (i < 80 ) && ( feof( stdin ) == 0 ); i++ )
   {
      buffer[i] = (char)ch;
      ch = _fgetchar();
   }

   // Add null to end string
   buffer[i] = '\0';
   printf( "%s\n", buffer );
}
```

```Output

      Line one.
Line two.Line one.
Line two.
```

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fputc, fputwc](fputc-fputwc.md)<br/>
[getc, getwc](getc-getwc.md)<br/>
