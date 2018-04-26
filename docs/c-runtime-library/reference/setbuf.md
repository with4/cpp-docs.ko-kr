---
title: setbuf | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- setbuf
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
- setbuf
dev_langs:
- C++
helpviewer_keywords:
- setbuf function
- stream buffering
ms.assetid: 13beda22-7b56-455d-8a6c-f2eb636885b9
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7a88ac98b8226b51ad036a0e31c919db9a63a0a0
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="setbuf"></a>setbuf

스트림 버퍼링을 제어합니다. 이 함수는 사용되지 않습니다. 대신 [setvbuf](setvbuf.md)를 사용하세요.

## <a name="syntax"></a>구문

```C
void setbuf(
   FILE *stream,
   char *buffer
);
```

### <a name="parameters"></a>매개 변수

*스트림* 에 대 한 포인터 **파일** 구조입니다.

*버퍼* 사용자가 할당 한 버퍼입니다.

## <a name="remarks"></a>설명

**setbuf** 함수에 대 한 버퍼링을 제어 *스트림*합니다. *스트림* 인수가 되지 읽거나 쓰지 않은 열려 있는 파일을 참조 해야 합니다. 경우는 *버퍼* 인수가 **NULL**, 스트림은 버퍼링 되지 않습니다. 버퍼의 길이 문자 배열 가리켜야 그렇지 않은 경우 **BUFSIZ**여기서 **BUFSIZ** STDIO에 정의 된 대로 버퍼 크기입니다. 8. 지정된 스트림에 대한 기본 시스템 할당 버퍼 대신 사용자 지정 버퍼가 I/O 버퍼링에 사용됩니다. **stderr** 기본적으로 스트림은 버퍼링 되지 않습니다 되지만 사용할 수 있습니다 **setbuf** 버퍼를 할당 하려면 **stderr**합니다.

**setbuf** 로 대체 되었습니다 [setvbuf](setvbuf.md), 새 코드에 대 한 기본 설정된 루틴인 변수인 합니다. **setbuf** 기존 코드와 호환성을 위해 유지 됩니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**setbuf**|\<stdio.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_setbuf.c
// compile with: /W3
// This program first opens files named DATA1 and
// DATA2. Then it uses setbuf to give DATA1 a user-assigned
// buffer and to change DATA2 so that it has no buffer.

#include <stdio.h>

int main( void )
{
   char buf[BUFSIZ];
   FILE *stream1, *stream2;

   fopen_s( &stream1, "data1", "a" );
   fopen_s( &stream2, "data2", "w" );

   if( (stream1 != NULL) && (stream2 != NULL) )
   {
      // "stream1" uses user-assigned buffer:
      setbuf( stream1, buf ); // C4996
      // Note: setbuf is deprecated; consider using setvbuf instead
      printf( "stream1 set to user-defined buffer at: %Fp\n", buf );

      // "stream2" is unbuffered
      setbuf( stream2, NULL ); // C4996
      printf( "stream2 buffering disabled\n" );
      _fcloseall();
   }
}
```

```Output
stream1 set to user-defined buffer at: 0012FCDC
stream2 buffering disabled
```

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[fflush](fflush.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[setvbuf](setvbuf.md)<br/>
