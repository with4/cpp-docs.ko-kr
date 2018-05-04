---
title: malloc | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- malloc
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
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- malloc
dev_langs:
- C++
helpviewer_keywords:
- malloc function
- memory allocation
ms.assetid: 144fcee2-be34-4a03-bb7e-ed6d4b99eea0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f600deb7bfa9b65ed9bdf784f2a16bd037729a51
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="malloc"></a>malloc

메모리 블록을 할당합니다.

## <a name="syntax"></a>구문

```C
void *malloc(
   size_t size
);
```

### <a name="parameters"></a>매개 변수

*size*<br/>
할당할 바이트입니다.

## <a name="return-value"></a>반환 값

**malloc** 할당 된 공간에 대 한 void 포인터를 반환 하거나 **NULL** 사용할 수 있는 메모리가 부족 한 경우. 이외의 형식에 대 한 포인터를 반환 하려면 **void**, 반환 값에 형식 캐스팅을 사용 합니다. 반환 값이 가리키는 저장소 공간은 맞춤 요구 사항이 기본 맞춤보다 작거나 같은 모든 형식의 개체 저장소에 적절하게 맞춰지도록 보장됩니다. (Visual c + +에서의 기본 맞춤은 맞춤에 대 한 필요한는 **double**, 또는 8 바이트입니다. 64비트 플랫폼을 대상으로 하는 코드에서는 16바이트입니다. 사용 하 여 [_aligned_malloc](aligned-malloc.md) 큰 맞춤 요구 사항에는 개체에 대 한 저장소를 할당 하-SSE 형식은 예를 들어 [__m128](../../cpp/m128.md) 및 **__m256**, 된 형식이 사용 하 여 선언 `__declspec(align( n ))` 여기서 **n** 8 보다 큽니다. 경우 *크기* 은 0으로, **malloc** 힙에서 빈 항목을 할당 하 고 해당 항목에 대 한 유효한 포인터를 반환 합니다. 반환 된 값을 항상 검사 **malloc**요청한 메모리 크기가 작은 경우에 합니다.

## <a name="remarks"></a>설명

**malloc** 함수 메모리 블록을 하나 이상 할당 *크기* 바이트입니다. 블록 보다 클 수 있습니다 *크기* 바이트 맞춤 및 유지 관리 정보에 대 한 필요한 공간 때문입니다.

**malloc** 설정 **errno** 를 **ENOMEM** 메모리 할당 실패 하거나 메모리 양을 초과 요청한 경우 **_HEAP_MAXREQ**합니다. 이 오류 및 다른 오류 코드에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.

시작 코드를 사용 하 여 **malloc** 저장소를 할당 하는 **_environ**, *envp*, 및 *argv* 변수입니다. 다음 함수 및 와이드 문자 대응 호출 또한 **malloc**합니다.

|||||
|-|-|-|-|
|[calloc](calloc.md)|[fscanf](fscanf-fscanf-l-fwscanf-fwscanf-l.md)|[_getw](getw.md)|[setvbuf](setvbuf.md)|
|[_exec 함수](../../c-runtime-library/exec-wexec-functions.md)|[fseek](fseek-fseeki64.md)|[_popen](popen-wpopen.md)|[_spawn 함수](../../c-runtime-library/spawn-wspawn-functions.md)|
|[fgetc](fgetc-fgetwc.md)|[fsetpos](fsetpos.md)|[printf](printf-printf-l-wprintf-wprintf-l.md)|[_strdup](strdup-wcsdup-mbsdup.md)|
|[_fgetchar](fgetc-fgetwc.md)|[_fullpath](fullpath-wfullpath.md)|[putc](putc-putwc.md)|[system](system-wsystem.md)|
|[fgets](fgets-fgetws.md)|[fwrite](fwrite.md)|[putchar](putc-putwc.md)|[_tempnam](tempnam-wtempnam-tmpnam-wtmpnam.md)|
|[fprintf](fprintf-fprintf-l-fwprintf-fwprintf-l.md)|[getc](getc-getwc.md)|[_putenv](putenv-wputenv.md)|[ungetc](ungetc-ungetwc.md)|
|[fputc](fputc-fputwc.md)|[getchar](getc-getwc.md)|[puts](puts-putws.md)|[vfprintf](vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)|
|[_fputchar](fputc-fputwc.md)|[_getcwd](getcwd-wgetcwd.md)|[_putw](putw.md)|[vprintf](vprintf-vprintf-l-vwprintf-vwprintf-l.md)|
|[fputs](fputs-fputws.md)|[_getdcwd](getcwd-wgetcwd.md)|[scanf](scanf-scanf-l-wscanf-wscanf-l.md)||
|[fread](fread.md)|[gets](../../c-runtime-library/gets-getws.md)|[_searchenv](searchenv-wsearchenv.md)||

C++ [_set_new_mode](set-new-mode.md) 함수는 **malloc**에 대한 새 처리기 모드를 설정합니다. 새 처리기 모드 나타냅니다 실패 여부 **malloc** 에서 설정한 대로 새 처리기 루틴을 호출 하는 것 [_set_new_handler](set-new-handler.md)합니다. 기본적으로 **malloc** 메모리 할당 실패 시 새 처리기 루틴을 호출 하지 않습니다. 이 기본 동작을 재정의할 수 있도록, **malloc** 가 메모리 할당에 실패 **malloc** 같은 새 처리기 루틴을 호출 방식으로 **새** 연산자는 때 이와 같은 이유로 실패 합니다. 기본값을 재정의 하려면 `_set_new_mode(1)` 초기에 프로그램 또는 NEWMODE에 링크 합니다. OBJ (참조 [링크 옵션](../../c-runtime-library/link-options.md)).

응용 프로그램은 C 런타임 라이브러리의 디버그 버전과 연결 되어 있으면 **malloc** 확인 [_malloc_dbg](malloc-dbg.md)합니다. 디버깅 프로세스 동안 힙을 관리하는 방법에 대한 자세한 내용은 [CRT 디버그 힙 정보](/visualstudio/debugger/crt-debug-heap-details)를 참조하세요.

**malloc** 표시 되어 `__declspec(noalias)` 및 `__declspec(restrict)`;이 함수가 전역 변수를 수정할 수 없도록 보장 되 고 반환 된 포인터 별칭이 지정 되지 않음을 의미 합니다. 자세한 내용은 [noalias](../../cpp/noalias.md) 및 [restrict](../../cpp/restrict.md)를 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**malloc**|\<stdlib.h> 및 \<malloc.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.

## <a name="example"></a>예제

```C
// crt_malloc.c
// This program allocates memory with
// malloc, then frees the memory with free.

#include <stdlib.h>   // For _MAX_PATH definition
#include <stdio.h>
#include <malloc.h>

int main( void )
{
   char *string;

   // Allocate space for a path name
   string = malloc( _MAX_PATH );

   // In a C++ file, explicitly cast malloc's return.  For example,
   // string = (char *)malloc( _MAX_PATH );

   if( string == NULL )
      printf( "Insufficient memory available\n" );
   else
   {
      printf( "Memory space allocated for path name\n" );
      free( string );
      printf( "Memory freed\n" );
   }
}
```

```Output
Memory space allocated for path name
Memory freed
```

## <a name="see-also"></a>참고자료

[메모리 할당](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[free](free.md)<br/>
[realloc](realloc.md)<br/>
[_aligned_malloc](aligned-malloc.md)<br/>
