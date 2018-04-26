---
title: clearerr | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- clearerr
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
- clearerr
dev_langs:
- C++
helpviewer_keywords:
- error indicator for streams
- resetting stream error indicator
- clearerr function
ms.assetid: a9711cd4-3335-43d4-a018-87bbac5b3bac
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8fbca4b6e6083cb22bc559b7bad7e75b00b8885c
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="clearerr"></a>clearerr

스트림에 대한 오류 표시기를 다시 설정합니다. 이 함수의 더 안전한 버전을 사용할 수 있습니다. [clearerr_s](clearerr-s.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
void clearerr(
   FILE *stream
);
```

### <a name="parameters"></a>매개 변수

*스트림* 에 대 한 포인터 **파일** 구조입니다.

## <a name="remarks"></a>설명

**clearerr** 함수에 대 한 파일 끝 표시기 및 오류 표시기 다시 설정 *스트림*합니다. 오류 표시기; 자동으로 제거 되지 않음 해당 스트림에서 작업을 계속 될 때까지 오류 값을 반환할 지정 된 스트림에 대 한 오류 표시기 설정 되 고 나면 **clearerr**, [fseek](fseek-fseeki64.md), **fsetpos**, 또는 [rewind](rewind.md) 호출 됩니다.

경우 *스트림* 은 **NULL**에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 이 함수를 설정 하는 경우 실행을 계속 허용 된, **errno** 를 **EINVAL** 를 반환 합니다. 대 한 자세한 내용은 **errno** 오류 코드 참조와 [errno 상수](../../c-runtime-library/errno-constants.md)합니다.

이 함수의 더 안전한 버전을 사용할 수 있습니다. [clearerr_s](clearerr-s.md)를 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**clearerr**|\<stdio.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_clearerr.c
// This program creates an error
// on the standard input stream, then clears
// it so that future reads won't fail.

#include <stdio.h>

int main( void )
{
   int c;
   // Create an error by writing to standard input.
   putc( 'c', stdin );
   if( ferror( stdin ) )
   {
      perror( "Write error" );
      clearerr( stdin );
   }

   // See if read causes an error.
   printf( "Will input cause an error? " );
   c = getc( stdin );
   if( ferror( stdin ) )
   {
      perror( "Read error" );
      clearerr( stdin );
   }
   else
      printf( "No read error\n" );
}
```

```Output

n

```

```Output

      nWrite error: No error
Will input cause an error? n
No read error
```

## <a name="see-also"></a>참고자료

[오류 처리](../../c-runtime-library/error-handling-crt.md)<br/>
[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[_eof](eof.md)<br/>
[feof](feof.md)<br/>
[ferror](ferror.md)<br/>
[perror, _wperror](perror-wperror.md)<br/>
