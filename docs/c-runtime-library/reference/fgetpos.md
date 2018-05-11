---
title: fgetpos | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- fgetpos
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
- fgetpos
dev_langs:
- C++
helpviewer_keywords:
- fgetpos function
- streams, file position indicator
ms.assetid: bfa05c38-1135-418c-bda1-d41be51acb62
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b111a911083354c8d9478b2c914a0a5f7dfe7725
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="fgetpos"></a>fgetpos

스트림의 파일 위치 표시기를 가져옵니다.

## <a name="syntax"></a>구문

```C
int fgetpos(
   FILE *stream,
   fpos_t *pos
);
```

### <a name="parameters"></a>매개 변수

*스트림*<br/>
대상 스트림입니다.

*pos*<br/>
위치 표시기 저장소입니다.

## <a name="return-value"></a>반환 값

성공 하면 **fgetpos** 0을 반환 합니다. 오류 시 0이 아닌 값을 반환 하 고 설정 **errno** 다음 중 하나에 매니페스트 상수 (STDIO에 정의 합니다. H): **EBADF**, 즉, 지정된 된 스트림에 올바른 파일 포인터가 아닌 없거나 액세스할 수, 또는 **EINVAL**, 즉은 *스트림* 값 이나 값*pos* 는 경우와 같이 유효 하거나가 null 포인터가 아닙니다. 경우 *스트림* 또는 *pos* 는 **NULL** 포인터, 함수 호출의 잘못 된 매개 변수 처리기에 설명 된 대로 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md).

## <a name="remarks"></a>설명

**fgetpos** 의 현재 값을 설정 하는 함수는 *스트림* 인수의 파일 위치 표시기 및 저장소에서 가리키는 개체에 *pos*합니다. **fsetpos** 함수에 저장 된 정보를 사용 하 여 나중에 수 *pos* 다시 설정 하는 *스트림* 시간에 해당 위치에 대 한 인수 포인터 **fgetpos** 호출 되었습니다. *pos* 값을 내부 형식에 저장 되 고 사용 하기 위한 에서만 **fgetpos** 및 **fsetpos**합니다.

## <a name="requirements"></a>요구 사항

|함수|필수 헤더|
|--------------|---------------------|
|**fgetpos**|\<stdio.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_fgetpos.c
// This program uses fgetpos and fsetpos to
// return to a location in a file.

#include <stdio.h>

int main( void )
{
   FILE   *stream;
   fpos_t pos;
   char   buffer[20];

   if( fopen_s( &stream, "crt_fgetpos.txt", "rb" ) ) {
      perror( "Trouble opening file" );
      return -1;
   }

   // Read some data and then save the position.
   fread( buffer, sizeof( char ), 8, stream );
   if( fgetpos( stream, &pos ) != 0 ) {
      perror( "fgetpos error" );
      return -1;
   }

   fread( buffer, sizeof( char ), 13, stream );
   printf( "after fgetpos: %.13s\n", buffer );

   // Restore to old position and read data
   if( fsetpos( stream, &pos ) != 0 ) {
      perror( "fsetpos error" );
      return -1;
   }

   fread( buffer, sizeof( char ), 13, stream );
   printf( "after fsetpos: %.13s\n", buffer );
   fclose( stream );
}
```

## <a name="input-crtfgetpostxt"></a>입력: crt_fgetpos.txt

```Input
fgetpos gets a stream's file-position indicator.
```

### <a name="output-crtfgetpostxt"></a>출력 crt_fgetpos.txt

```Output
after fgetpos: gets a stream
after fsetpos: gets a stream
```

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fsetpos](fsetpos.md)<br/>
