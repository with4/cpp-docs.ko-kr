---
title: fflush | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- fflush
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
- fflush
dev_langs:
- C++
helpviewer_keywords:
- streams, flushing
- flushing
- fflush function
ms.assetid: 8bbc753f-dc74-4e77-b563-74da2835e92b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 72f0812e713d0d474363dcc5f79cc11eddb46020
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="fflush"></a>fflush

스트림을 플러시합니다.

## <a name="syntax"></a>구문

```C
int fflush(
   FILE *stream
);
```

### <a name="parameters"></a>매개 변수

*스트림*<br/>
**FILE** 구조체에 대한 포인터입니다.

## <a name="return-value"></a>반환 값

**fflush** 버퍼 플러시 되었습니다 성공적으로 0을 반환 합니다. 지정된 스트림에 버퍼가 없거나 해당 스트림이 읽기 전용으로 열린 경우에도 값 0이 반환됩니다. 반환 값이 **EOF** 은 오류를 나타냅니다.

> [!NOTE]
> 경우 **fflush** 반환 **EOF**, 데이터 쓰기 오류로 인해 손실 되었을 수 있습니다. 이 버퍼링 하지 않으려면와 안전에 중요 한 오류 처리기를 설정 하는 경우는 **setvbuf** 함수 또는 같은 하위 수준 I/O 루틴을 사용 하려면 **_open**, **_close**, 및 **_write** 스트림 I/O 함수 대신 합니다.

## <a name="remarks"></a>설명

**fflush** 함수 스트림도 플러시합니다 *스트림*합니다. 스트림이 쓰기 모드에서 열렸거나 업데이트 모드에서 열리고 마지막 작업이 쓰기였던 경우 스트림 버퍼의 콘텐츠가 기본 파일 또는 장치에 기록되고 버퍼가 삭제됩니다. 스트림이 읽기 모드로 열린 있거나 스트림이 없는 버퍼에 대 한 호출의 **fflush** 아무 효과가 없으며 모든 버퍼에서 유지 됩니다. 에 대 한 호출 **fflush** 모든 이전 호출의 결과가 무시 **ungetc** 스트림에 대 한 합니다. 스트림은 호출 후에 열려 있습니다.

경우 *스트림* 은 **NULL**, 동작에 대 한 호출 같습니다 **fflush** 각 열린 스트림에 대. 쓰기 모드로 열린 모든 스트림과 마지막 작업이 쓰기인 업데이트 모드로 열린 모든 스트림이 플러시됩니다. 이 호출은 다른 스트림에 영향을 미치지 않습니다.

버퍼는 보통 운영 체제에서 유지 관리됩니다. 운영 체제에서는 버퍼가 가득 찼을 때, 스트림이 닫혀 있을 때, 스트림을 닫지 않고 프로그램이 정상적으로 종료될 때 등 디스크에 데이터를 자동으로 쓰는 최적의 시간을 결정합니다. 런타임 라이브러리의 디스크에 커밋 기능을 사용하면 중요한 데이터가 운영 체제 버퍼 대신 디스크에 직접 기록되어 있는지 확인할 수 있습니다. 기존 프로그램을 다시 작성하지 않고 프로그램의 개체 파일을 COMMODE.OBJ에 연결하여 이 기능을 사용할 수 있습니다. 결과 실행 파일에서 호출 **_flushall** 모든 버퍼의 내용이 디스크에 쓰여집니다. 만 **_flushall** 및 **fflush** COMMODE.OBJ의 영향을 받는 합니다.

디스크에 커밋 기능을 제어하는 방법에 대한 자세한 내용은 [스트림 I/O](../../c-runtime-library/stream-i-o.md), [fopen](fopen-wfopen.md) 및 [_fdopen](fdopen-wfdopen.md)을 참조하세요.

이 함수는 호출 스레드를 잠그므로 스레드로부터 안전합니다. 잠기지 않는 버전에 대 한 참조 **_fflush_nolock**합니다.

## <a name="requirements"></a>요구 사항

|함수|필수 헤더|
|--------------|---------------------|
|**fflush**|\<stdio.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_fflush.c
#include <stdio.h>
#include <conio.h>

int main( void )
{
   int integer;
   char string[81];

   // Read each word as a string.
   printf( "Enter a sentence of four words with scanf: " );
   for( integer = 0; integer < 4; integer++ )
   {
      scanf_s( "%s", string, sizeof(string) );
      printf( "%s\n", string );
   }

   // You must flush the input buffer before using gets.
   // fflush on input stream is an extension to the C standard
   fflush( stdin );
   printf( "Enter the same sentence with gets: " );
   gets_s( string, sizeof(string) );
   printf( "%s\n", string );
}
```

```Output

      This is a test
This is a test

```

```Output

      This is a test
This is a testEnter a sentence of four words with scanf: This is a test
This
is
a
test
Enter the same sentence with gets: This is a test
This is a test
```

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[_flushall](flushall.md)<br/>
[setvbuf](setvbuf.md)<br/>
