---
title: "malloc | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 65b70ba6be4837a36d5987e60b1d7229134ceb99
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="malloc"></a>malloc
메모리 블록을 할당합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void *malloc(  
   size_t size   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `size`  
 할당할 바이트입니다.  
  
## <a name="return-value"></a>반환 값  
 `malloc`는 할당된 공간에 대한 void 포인터를 반환하거나 사용 가능한 메모리가 부족한 경우 `NULL`을 반환합니다. `void`가 아닌 형식에 대한 포인터를 반환하려면 반환 값에 형식 캐스팅을 사용하세요. 반환 값이 가리키는 저장소 공간은 맞춤 요구 사항이 기본 맞춤보다 작거나 같은 모든 형식의 개체 저장소에 적절하게 맞춰지도록 보장됩니다. Visual C++에서 기본 맞춤은 `double`에 필요한 맞춤이거나 8바이트입니다. 64비트 플랫폼을 대상으로 하는 코드에서는 16바이트입니다. [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md)를 사용하여 맞춤 요구 사항이 더 큰 개체에 대해 저장소를 할당합니다. 예를 들어 SSE 형식 [__m128](../../cpp/m128.md) 및 `__m256`과 `__declspec(align( n ))`를 사용하여 선언된 형식(여기서 `n`은 8보다 큼)이 있습니다. `size`가 0이면 `malloc`는 힙에서 길이가 0인 항목을 할당하고 해당 항목에 대한 유효한 포인터를 반환합니다. 요청된 메모리의 양이 작은 경우에도 `malloc`의 반환 값을 항상 확인하세요.  
  
## <a name="remarks"></a>설명  
 `malloc` 함수는 `size`바이트 이상의 메모리 블록을 할당합니다. 이 블록은 맞춤 및 유지 관리 정보에 필요한 공간이기 때문에 `size`보다 클 수 있습니다.  
  
 메모리 할당에 실패하거나 요청된 메모리의 양이 `_HEAP_MAXREQ`를 초과하는 경우 `malloc`는 `errno`를 `ENOMEM`으로 설정합니다. 이 오류 및 다른 오류 코드에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.  
  
 시작 코드는 `malloc`를 사용하여 `_environ`, `envp` 및 `argv` 변수에 대해 저장소를 할당합니다. 다음 함수 및 해당 와이드 문자 함수도 `malloc`를 호출합니다.  
  
|||||  
|-|-|-|-|  
|[calloc](../../c-runtime-library/reference/calloc.md)|[fscanf](../../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)|[_getw](../../c-runtime-library/reference/getw.md)|[setvbuf](../../c-runtime-library/reference/setvbuf.md)|  
|[_exec 함수](../../c-runtime-library/exec-wexec-functions.md)|[fseek](../../c-runtime-library/reference/fseek-fseeki64.md)|[_popen](../../c-runtime-library/reference/popen-wpopen.md)|[_spawn 함수](../../c-runtime-library/spawn-wspawn-functions.md)|  
|[fgetc](../../c-runtime-library/reference/fgetc-fgetwc.md)|[fsetpos](../../c-runtime-library/reference/fsetpos.md)|[printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)|[_strdup](../../c-runtime-library/reference/strdup-wcsdup-mbsdup.md)|  
|[_fgetchar](../../c-runtime-library/reference/fgetc-fgetwc.md)|[_fullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)|[putc](../../c-runtime-library/reference/putc-putwc.md)|[system](../../c-runtime-library/reference/system-wsystem.md)|  
|[fgets](../../c-runtime-library/reference/fgets-fgetws.md)|[fwrite](../../c-runtime-library/reference/fwrite.md)|[putchar](../../c-runtime-library/reference/putc-putwc.md)|[_tempnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)|  
|[fprintf](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)|[getc](../../c-runtime-library/reference/getc-getwc.md)|[_putenv](../../c-runtime-library/reference/putenv-wputenv.md)|[ungetc](../../c-runtime-library/reference/ungetc-ungetwc.md)|  
|[fputc](../../c-runtime-library/reference/fputc-fputwc.md)|[getchar](../../c-runtime-library/reference/getc-getwc.md)|[puts](../../c-runtime-library/reference/puts-putws.md)|[vfprintf](../../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)|  
|[_fputchar](../../c-runtime-library/reference/fputc-fputwc.md)|[_getcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)|[_putw](../../c-runtime-library/reference/putw.md)|[vprintf](../../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md)|  
|[fputs](../../c-runtime-library/reference/fputs-fputws.md)|[_getdcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)|[scanf](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)||  
|[fread](../../c-runtime-library/reference/fread.md)|[gets](../../c-runtime-library/gets-getws.md)|[_searchenv](../../c-runtime-library/reference/searchenv-wsearchenv.md)||  
  
 C++ [_set_new_mode](../../c-runtime-library/reference/set-new-mode.md) 함수는 `malloc`에 대해 새 처리기 모드를 설정합니다. 새 처리기 모드는 실패 시 `malloc`가 [_set_new_handler](../../c-runtime-library/reference/set-new-handler.md)에서 설정한 대로 새 처리기 루틴을 호출하는지 여부를 나타냅니다. 기본적으로 `malloc`는 메모리 할당 실패 시 새 처리기 루틴을 호출하지 않습니다. `malloc`가 메모리 할당에 실패한 경우 `malloc`이 `new` 연산자가 같은 이유로 실패했을 때 수행하는 것과 동일한 방식으로 새 처리기 루틴을 호출하도록 이 기본 동작을 재정의할 수 있습니다. 기본값을 재정의 하려면 `_set_new_mode(1)` 초기에 프로그램 또는 NEWMODE에 링크 합니다. OBJ (참조 [링크 옵션](../../c-runtime-library/link-options.md)).  
  
 응용 프로그램이 디버그 버전의 C 런타임 라이브러리에 연결되면 `malloc`는 [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md)가 됩니다. 디버깅 프로세스 동안 힙을 관리하는 방법에 대한 자세한 내용은 [CRT 디버그 힙 정보](/visualstudio/debugger/crt-debug-heap-details)를 참조하세요.  
  
 `malloc`는 `__declspec(noalias)` 및 `__declspec(restrict)`로 표시되며, 이는 함수가 전역 변수를 수정할 수 없도록 보장되고 반환된 포인터에 별칭이 지정되지 않음을 의미합니다. 자세한 내용은 [noalias](../../cpp/noalias.md) 및 [restrict](../../cpp/restrict.md)를 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`malloc`|\<stdlib.h> 및 \<malloc.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="libraries"></a>라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## <a name="example"></a>예  
  
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
  
## <a name="see-also"></a>참고 항목  
 [메모리 할당](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md)
