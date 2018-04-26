---
title: ftell, _ftelli64 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _ftelli64
- ftell
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
- _ftelli64
- ftell
dev_langs:
- C++
helpviewer_keywords:
- ftell function
- ftelli64 function
- _ftelli64 function
- file pointers [C++], getting current position
- file pointers [C++]
ms.assetid: 40149cd8-65f2-42ff-b70c-68e3e918cdd7
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3661f4fa36ff83ca47a4847ff416edb3cef0c2fc
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="ftell-ftelli64"></a>ftell, _ftelli64

파일 포인터의 현재 위치를 가져옵니다.

## <a name="syntax"></a>구문

```C
long ftell(
   FILE *stream
);
__int64 _ftelli64(
   FILE *stream
);
```

### <a name="parameters"></a>매개 변수

*스트림*<br/>
대상 **파일** 구조입니다.

## <a name="return-value"></a>반환 값

**ftell** 및 **_ftelli64** 현재 파일 위치를 반환 합니다. 반환한 값 **ftell** 및 **_ftelli64** 텍스트 모드를 사용 하면 캐리지 리턴-줄 바꿈 변환 하기 때문에 텍스트 모드에서 연 스트림에 대 한 실제 바이트 오프셋을 반영 하지 않을 수 있습니다. 사용 하 여 **ftell** 와 [fseek](fseek-fseeki64.md) 또는 **_ftelli64** 와 [_fseeki64](fseek-fseeki64.md) 파일 위치를 올바르게 돌아갑니다. 오류 시 **ftell** 및 **_ftelli64** 에 설명 된 대로 잘못 된 매개 변수 처리기를 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 이러한 함수 반환-1l 및 집합을 계속 하려면 실행 허용 된 경우 **errno** ERRNO에 정의 된 두 상수 중 하나에 있습니다. 8. **EBADF** 상수 의미는 *스트림* 인수가 잘못 된 파일 포인터 값 이거나 열려 있는 파일을 참조 하지 않습니다. **EINVAL** 잘못 된 의미 *스트림* 함수에 인수가 전달 되었습니다. (예: 터미널 및 프린터) 찾기를 수행할 수 없는 장치 또는 때 *스트림* 참조 하지 않는 열려 있는 파일을 반환 값이 정의 합니다.

이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

## <a name="remarks"></a>설명

**ftell** 및 **_ftelli64** 와 연결 된 파일 포인터 (있는 경우)의 현재 위치를 검색 하는 함수 *스트림*합니다. 위치는 스트림 시작을 기준으로 하는 오프셋으로 표현됩니다.

데이터를 추가하기 위해 파일이 열리면 현재 파일 위치는 다음 쓰기가 수행되는 위치가 아니라 마지막 I/O 작업에 의해 결정됩니다. 예를 들어 파일이 추가를 위해 열리고 마지막 작업이 읽기였다면 파일 위치는 다음 쓰기가 시작되는 위치가 아니라 다음 읽기 작업이 시작되는 지점입니다. 파일이 추가를 위해 열린 경우 파일 위치는 쓰기 작업 전에 파일의 끝으로 이동합니다. 추가를 위해 열린 파일에서 I/O 작업이 아직 수행되지 않은 경우 파일 위치는 파일의 시작입니다.

텍스트 모드에서 Ctrl+Z는 입력 시 파일 끝 문자로 해석됩니다. 읽기/쓰기를 위해 열려 있는 파일에서 **fopen** 및 모든 관련된 루틴 파일의 끝에 CTRL + Z를 확인 하 고 가능한 경우 제거 합니다. 조합을 사용 하 여 때문에 이렇게 **ftell** 및 [fseek](fseek-fseeki64.md) 또는 **_ftelli64** 및 [_fseeki64](fseek-fseeki64.md)로 끝나는 파일 내에서 이동 합니다. CTRL + Z 않을 **ftell** 또는 **_ftelli64** 파일의 끝 부분에서 제대로 동작 하지 합니다.

이 함수는 실행 중에 호출 스레드를 잠그므로 스레드로부터 안전합니다. 잠기지 않는 버전에 대 한 참조 **_ftell_nolock**합니다.

## <a name="requirements"></a>요구 사항

|함수|필수 헤더|선택적 헤더|
|--------------|---------------------|----------------------|
|**ftell**|\<stdio.h>|\<errno.h>|
|**_ftelli64**|\<stdio.h>|\<errno.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_ftell.c
// This program opens a file named CRT_FTELL.C
// for reading and tries to read 100 characters. It
// then uses ftell to determine the position of the
// file pointer and displays this position.

#include <stdio.h>

FILE *stream;

int main( void )
{
   long position;
   char list[100];
   if( fopen_s( &stream, "crt_ftell.c", "rb" ) == 0 )
   {
      // Move the pointer by reading data:
      fread( list, sizeof( char ), 100, stream );
      // Get position after read:
      position = ftell( stream );
      printf( "Position after trying to read 100 bytes: %ld\n",
              position );
      fclose( stream );
   }
}
```

```Output
Position after trying to read 100 bytes: 100
```

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[fgetpos](fgetpos.md)<br/>
[fseek, _fseeki64](fseek-fseeki64.md)<br/>
[_lseek, _lseeki64](lseek-lseeki64.md)<br/>
