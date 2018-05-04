---
title: clearerr_s | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- clearerr_s
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
- clearerr_s
dev_langs:
- C++
helpviewer_keywords:
- error indicator for streams
- resetting stream error indicator
- clearerr_s function
ms.assetid: b74d014d-b7a8-494a-a330-e5ffd5614772
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 03259f0eff64eb23af87ae18dc68272b5a0bd02f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="clearerrs"></a>clearerr_s

스트림에 대한 오류 표시기를 다시 설정합니다. [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 기능이 향상된 [clearerr](clearerr.md) 버전입니다.

## <a name="syntax"></a>구문

```C
errno_t clearerr_s(
   FILE *stream
);
```

### <a name="parameters"></a>매개 변수

*스트림*<br/>
에 대 한 포인터 **파일** 구조

## <a name="return-value"></a>반환 값

성공 하면 0이 **EINVAL** 경우 *스트림* 은 NULL입니다.

## <a name="remarks"></a>설명

**clearerr_s** 함수에 대 한 파일 끝 표시기 및 오류 표시기 다시 설정 *스트림*합니다. 오류 표시기; 자동으로 제거 되지 않음 해당 스트림에서 작업을 계속 될 때까지 오류 값을 반환할 지정 된 스트림에 대 한 오류 표시기 설정 되 고 나면 **clearerr_s**, **clearerr**, [fseek](fseek-fseeki64.md), **fsetpos**, 또는 [rewind](rewind.md) 호출 됩니다.

경우 *스트림* 가 null 인 경우에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 이 함수를 설정 하는 경우 실행을 계속 허용 된, **errno** 를 **EINVAL** 반환 **EINVAL**합니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**clearerr_s**|\<stdio.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_clearerr_s.c
// This program creates an error
// on the standard input stream, then clears
// it so that future reads won't fail.

#include <stdio.h>

int main( void )
{
   int c;
   errno_t err;

   // Create an error by writing to standard input.
   putc( 'c', stdin );
   if( ferror( stdin ) )
   {
      perror( "Write error" );
      err = clearerr_s( stdin );
      if (err != 0)
      {
         abort();
      }
   }

   // See if read causes an error.
   printf( "Will input cause an error? " );
   c = getc( stdin );
   if( ferror( stdin ) )
   {
      perror( "Read error" );
      err = clearerr_s( stdin );
      if (err != 0)
      {
         abort();
      }
   }
}
```

```Output

n

```

```Output

      nWrite error: Bad file descriptor
Will input cause an error? n
```

## <a name="see-also"></a>참고자료

[오류 처리](../../c-runtime-library/error-handling-crt.md)<br/>
[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[clearerr](clearerr.md)<br/>
[_eof](eof.md)<br/>
[feof](feof.md)<br/>
[ferror](ferror.md)<br/>
[perror, _wperror](perror-wperror.md)<br/>
