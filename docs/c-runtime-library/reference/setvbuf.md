---
title: setvbuf | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- setvbuf
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
- setvbuf
dev_langs:
- C++
helpviewer_keywords:
- controlling stream buffering
- stream buffering
- setvbuf function
ms.assetid: 6aa5aa37-3408-4fa0-992f-87f9f9c4baea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4c516932eb8d50fb8c9fdbe6f8c48a3f590b1ffb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32408486"
---
# <a name="setvbuf"></a>setvbuf

스트림 버퍼링 및 버퍼 크기를 제어합니다.

## <a name="syntax"></a>구문

```C
int setvbuf(
   FILE *stream,
   char *buffer,
   int mode,
   size_t size
);
```

### <a name="parameters"></a>매개 변수

*스트림*<br/>
**FILE** 구조체에 대한 포인터입니다.

*buffer*<br/>
사용자가 할당한 버퍼입니다.

*모드*<br/>
버퍼링 모드입니다.

*size*<br/>
버퍼 크기(바이트)입니다. 허용 범위: 2 < = *크기* < = INT_MAX (2147483647). 제공 된 값에 내부적으로 *크기* 2의 가장 가까운 배수로 내림 합니다.

## <a name="return-value"></a>반환 값

성공하면 0을 반환합니다.

경우 *스트림* 은 **NULL**, if 또는 *모드* 또는 *크기* 은 올바른 변경 내용, 내에 있지는 잘못 된 매개 변수 처리기가 호출에 설명 된 대로 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 이 함수는-1 반환 하 고 집합을 계속 하려면 실행 허용 된 경우 **errno** 를 **EINVAL**합니다.

이러한 오류 코드 및 기타 오류 코드에 대한 내용은 [_doserrno, errno, _sys_errlist, 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

## <a name="remarks"></a>설명

**setvbuf** 기능을 사용 하면 프로그램을 모두 버퍼링을 제어 하 고 버퍼 크기에 대 한 *스트림*합니다. *스트림* 열린 이후에 I/O 작업을 수행 하지에 열려 있는 파일을 참조 해야 합니다. 가 가리키는 배열의 *버퍼* 하지 않은 경우 버퍼를 사용 **NULL**있으며이 경우 **setvbuf** 는 자동으로 할당 된 버퍼의 길이 사용 하 여 *크기* /2 * 2 바이트입니다.

모드는 해야 **_IOFBF**, **_IOLBF**, 또는 **_IONBF**합니다. 경우 *모드* 은 **_IOFBF** 또는 **_IOLBF**, 다음 *크기* 버퍼의 크기로 사용 됩니다. 경우 *모드* 은 **_IONBF**, 스트림이 버퍼링 및 *크기* 및 *버퍼* 무시 됩니다. 에 대 한 값 *모드* 는 해당 의미 및:

|*모드* 값|의미|
|-|-|
**_IOFBF**|전체 버퍼링; 즉, *버퍼* 버퍼 사용 및 *크기* 버퍼의 크기로 사용 됩니다. 경우 *버퍼* 은 **NULL**, 자동으로 할당 된 버퍼 *크기* 바이트 길이의 사용 됩니다.
**_IOLBF**|이 값을 사용하는 경우 라인 버퍼링이 제공되는 시스템도 있습니다. 그러나, Win32에 대 한 동작은 동일 **_IOFBF** -전체 버퍼링 합니다.
**_IONBF**|버퍼가에 관계 없이 사용 되는 *버퍼* 또는 *크기*합니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**setvbuf**|\<stdio.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.

## <a name="example"></a>예제

```C
// crt_setvbuf.c
// This program opens two streams: stream1
// and stream2. It then uses setvbuf to give stream1 a
// user-defined buffer of 1024 bytes and stream2 no buffer.
//

#include <stdio.h>

int main( void )
{
   char buf[1024];
   FILE *stream1, *stream2;

   if( fopen_s( &stream1, "data1", "a" ) == 0 &&
       fopen_s( &stream2, "data2", "w" ) == 0 )
   {
      if( setvbuf( stream1, buf, _IOFBF, sizeof( buf ) ) != 0 )
         printf( "Incorrect type or size of buffer for stream1\n" );
      else
         printf( "'stream1' now has a buffer of 1024 bytes\n" );
      if( setvbuf( stream2, NULL, _IONBF, 0 ) != 0 )
         printf( "Incorrect type or size of buffer for stream2\n" );
      else
         printf( "'stream2' now has no buffer\n" );
      _fcloseall();
   }
}
```

```Output
'stream1' now has a buffer of 1024 bytes
'stream2' now has no buffer
```

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[fflush](fflush.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[setbuf](setbuf.md)<br/>
