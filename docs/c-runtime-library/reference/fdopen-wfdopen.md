---
title: _fdopen, _wfdopen | Microsoft 문서
ms.custom: ''
ms.date: 12/12/2017
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _fdopen
- _wfdopen
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
apitype: DLLExport
f1_keywords:
- _tfdopen
- _fdopen
- _wfdopen
- wfdopen
- tfdopen
dev_langs:
- C++
helpviewer_keywords:
- wfdopen function
- _fdopen function
- _wfdopen function
- tfdopen function
- fdopen function
- _tfdopen function
- streams, associating with files
ms.assetid: 262757ff-1e09-4472-a5b6-4325fc28f971
caps.latest.revision: 23
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 03dd7c56c8b8249ddee09ed2ac5446f99484e671
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="fdopen-wfdopen"></a>_fdopen, _wfdopen

하위 수준 I/O를 위해 이전에 연 파일에 스트림을 연결합니다.

## <a name="syntax"></a>구문

```C
FILE *_fdopen(
   int fd,
   const char *mode
);
FILE *_wfdopen(
   int fd,
   const wchar_t *mode
);
```

### <a name="parameters"></a>매개 변수

*fd* 열려 있는 파일의 파일 설명자입니다.

*모드* 파일 액세스의 유형입니다.

## <a name="return-value"></a>반환 값

각 함수는 열린 스트림에 대한 포인터를 반환합니다. null 포인터 값은 오류를 나타냅니다. 오류가 발생하는 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 실행을 계속 하도록 허용 된 경우 **errno** 도 설정 **EBADF**, 잘못 된 파일 설명자를 나타내는 또는 **EINVAL**, 않는다는 의미 *모드*  는 null 포인터입니다.

이 오류 및 다른 오류 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.

## <a name="remarks"></a>설명

**_fdopen** 로 식별 되는 파일과 I/O 스트림을 연결 하는 함수 *fd*, 따라서 버퍼링 되 고 서식이 지정 된 하위 수준 I/O에 대 한 열려 있는 파일 수 있습니다. **_wfdopen** 의 와이드 문자 버전이 **_fdopen**; *모드* 인수를 **_wfdopen** 는 와이드 문자 문자열입니다. **_wfdopen** 및 **_fdopen** 그렇지 않으면 동일 하 게 작동 합니다.

파일 설명자에 전달 된 **_fdopen** 소유가 **파일 &#42;**  스트림 합니다. 경우 **_fdopen** 성공적으로 호출 하지 마십시오 [ \_닫습니다](close.md) 파일 설명자에 있습니다. 호출 [fclose](fclose-fcloseall.md) 반환 된 **파일 &#42;**  또한 파일 설명자를 종료 합니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|Tchar.h 루틴|\_유니코드 및 \_MBCS 정의 되지 않았습니다|\_MBCS 정의|\_유니코드 정의|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tfdopen**|**_fdopen**|**_fdopen**|**_wfdopen**|

*모드* 문자열 파일에 대 한 요청 된 파일 액세스의 유형을 지정 합니다.

|*모드*|액세스|
|-|-|
**"r"**|읽기 위해 엽니다. 파일이 존재 하지 않거나 찾을 수 없는 경우는 **fopen** 호출이 실패 합니다.
**"w"**|쓰기 위해 빈 파일을 엽니다. 지정한 파일이 있으면 이 파일의 내용은 삭제됩니다.
**"a"**|(추가) 파일의 끝에 쓰기 위해 엽니다. 파일이 없는 경우 파일을 만듭니다.
**"r+"**|읽고 쓰기 위해 엽니다. 파일이 있어야 합니다.
**"w+"**|읽고 쓰기 위해 빈 파일을 엽니다. 파일이 있으면 이 파일의 내용은 삭제됩니다.
**"a+"**|읽고 추가하기 위해 엽니다. 파일이 없는 경우 파일을 만듭니다.

와 파일이 열릴 때의 **"a"** 또는 **"a +"** 액세스 형식을 모든 쓰기 작업이 파일의 끝에서 발생 합니다. 사용 하 여 파일 포인터 위치를 변경할 수 [fseek](fseek-fseeki64.md) 또는 [되감기](rewind.md), 항상 이동 다시 파일의 끝에 쓰기 작업을 수행 하기 전에 하지만 합니다. 따라서 기존 데이터를 덮어쓸 수 없습니다. 경우는 **"r +"**, **"w +"**, 또는 **"a +"** 액세스 형식을 지정한 경우 읽기와 쓰기가 모두 허용 됩니다 ("업데이트" 용으로 열립니다, 파일이 업데이트용). 그러나 읽기와 쓰기를 전환할 때 있어야 한 장애가 [fflush](fflush.md), [fsetpos](fsetpos.md), [fseek](fseek-fseeki64.md), 또는 [되감기](rewind.md) 작업입니다. 에 대 한 현재 위치를 지정할 수는 [fsetpos](fsetpos.md) 또는 [fseek](fseek-fseeki64.md) 작업을 하려는 경우.

위의 값 외에도 문자 수에 포함 될 수도 *모드* 줄 바꿈 문자에 대 한 변환 모드를 지정 하려면:

|*모드* 한정자|동작|
|-|-|
**t**|텍스트(변환됨) 모드에서 엽니다. 이 모드에서는 CR-LF(캐리지 리턴 줄 바꿈) 조합은 입력 시 단일 LF(줄 바꿈)로 변환되고, LF 문자는 출력 시 CR-LF 조합으로 변환됩니다. 또한 CTRL+Z는 입력 시 파일 끝 문자로 변환됩니다.
**b**|이진(변환되지 않음) 모드에서 엽니다. 모든 변환은 **t** 모드는 표시 되지 않습니다.
**c**|연결 된 작업에 대 한 커밋 플래그를 사용 *filename* 파일 버퍼의 내용이 디스크에 직접 기록 되도록 **fflush** 또는 **_flushall** 호출 됩니다.
**n**|연결 된 작업에 대 한 커밋 플래그를 다시 설정 *filename* 를 "커밋 안 함." 이 값이 기본값입니다. 또한 프로그램을 Commode.obj와 연결할 경우 전역 커밋 플래그를 재정의합니다. 프로그램을 Commode.obj와 명시적으로 연결하지 않을 경우 전역 커밋 플래그 기본값은 "커밋 안 함"입니다.

**t**, **c**, 및 **n** *모드* 옵션에 대 한 Microsoft 확장은 **fopen** 및 **_fdopen**합니다. ANSI 이식성을 유지하려는 경우에는 사용하지 마세요.

경우 **t** 또는 **b** 제공 되지 않습니다 *모드*, 기본 변환 모드는 전역 변수에 의해 정의 됩니다 [ \_fmode](../../c-runtime-library/fmode.md)합니다. 경우 **t** 또는 **b** 은 오류가 발생 하는 인수에 접두어로 추가 되 고 NULL을 반환 합니다. 텍스트 모드와 이진 모드에 대한 자세한 내용은 [텍스트 및 이진 모드 파일 I/O](../../c-runtime-library/text-and-binary-mode-file-i-o.md)를 참조하세요.

에 유효한 문자는 *모드* 에 사용 되는 문자열 **fopen** 및 **_fdopen** 에 해당 *oflag* 에 사용 되는 인수 [ \_열고](open-wopen.md) 및 [ \_sopen](sopen-wsopen.md)이 표에 표시 된 것 처럼:

|문자 *모드* 문자열|해당 *oflag* 값 **_open** 및 **_sopen**|
|---------------------------------|---------------------------------------------------|
|**a**|**\_O\_WRONLY &#124; \_O\_APPEND** (일반적으로  **\_O\_WRONLY &#124; \_O\_CREAT &#124; \_O \_APPEND**)|
|**+**|**\_O\_RDWR &#124; \_O\_APPEND** (일반적으로  **\_O\_RDWR &#124; \_O\_APPEND &#124; \_O\_ CREAT** )|
|**r**|**\_O\_RDONLY**|
|**r +**|**\_O\_RDWR**|
|**w**|**\_O\_WRONLY** (일반적으로  **\_O\_WRONLY &#124; \_O\_CREAT &#124; \_O\_TRUNC**)|
|**w +**|**\_O\_RDWR** (일반적으로  **\_O\_RDWR &#124; \_O\_CREAT &#124; \_O\_TRUNC**)|
|**b**|**\_O\_이진**|
|**t**|**\_O\_TEXT**|
|**c**|없음|
|**n**|없음|

## <a name="requirements"></a>요구 사항

|함수|필수 헤더|
|--------------|---------------------|
|**_fdopen**|\<stdio.h>|
|**_wfdopen**|\<stdio.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```c
// crt_fdopen.c
// This program opens a file by using low-level
// I/O, then uses _fdopen to switch to stream
// access. It counts the lines in the file.

#include <stdlib.h>
#include <stdio.h>
#include <fcntl.h>
#include <io.h>
#include <share.h>

int main( void )
{
   FILE *stream;
   int  fd, count = 0;
   char inbuf[128];

   // Open a file.
   if( _sopen_s( &fd, "crt_fdopen.txt", _O_RDONLY, _SH_DENYNO, 0 ) )
      exit( 1 );

   // Get stream from file descriptor.
   if( (stream = _fdopen( fd, "r" )) == NULL )
      exit( 1 );

   while( fgets( inbuf, 128, stream ) != NULL )
      count++;

   // After _fdopen, close by using fclose, not _close.
   fclose( stream );
   printf( "Lines in file: %d\n", count );
}
```

### <a name="input-crtfdopentxt"></a>입력: crt_fdopen.txt

```Input
Line one
Line two
```

### <a name="output"></a>출력

```Output
Lines in file: 2
```

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[\_dup, \_dup2](dup-dup2.md)<br/>
[fclose, \_fcloseall](fclose-fcloseall.md)<br/>
[fopen, \_wfopen](fopen-wfopen.md)<br/>
[freopen, \_wfreopen](freopen-wfreopen.md)<br/>
[\_open, \_wopen](open-wopen.md)<br/>
