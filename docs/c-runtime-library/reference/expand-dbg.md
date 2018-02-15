---
title: "_expand_dbg | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _expand_dbg
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
- expand_dbg
- _expand_dbg
dev_langs:
- C++
helpviewer_keywords:
- memory blocks, changing size
- expand_dbg function
- _expand_dbg function
ms.assetid: dc58c91f-72a8-48c6-b643-fe130fb6c1fd
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 41f3d59cec6ec4a064143e0211ebd956f30e16e5
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="expanddbg"></a>_expand_dbg
블록을 확장하거나 축소하여 힙에서 지정된 메모리 블록의 크기를 조정합니다(디버그 버전에만 해당).  
  
## <a name="syntax"></a>구문  
  
```  
void *_expand_dbg(   
   void *userData,  
   size_t newSize,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `userData`  
 이전에 할당된 메모리 블록에 대한 포인터입니다.  
  
 `newSize`  
 요청된 블록의 새 크기(바이트)입니다.  
  
 `blockType`  
 크기가 조정된 블록의 요청된 형식: `_CLIENT_BLOCK` 또는 `_NORMAL_BLOCK`.  
  
 `filename`  
 확장 작업 또는 `NULL`을 요청한 소스 파일의 이름에 대한 포인터입니다.  
  
 `linenumber`  
 확장 작업이 요청되었거나 `NULL`인 소스 파일의 줄 번호입니다.  
  
 `filename` 및 `linenumber` 매개 변수는 `_expand_dbg`가 명시적으로 호출되었거나 [_CRTDBG_MAP_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md) 전처리기 상수가 정의된 경우에만 사용할 수 있습니다.  
  
## <a name="return-value"></a>반환 값  
 성공적으로 완료되면 `_expand_dbg`는 크기가 조정된 메모리 블록의 포인터를 반환합니다. 메모리가 이동되지 않으므로 주소는 userData와 같습니다. 오류가 발생했거나 블록을 요청된 크기로 확장할 수 없는 경우 `NULL`이 반환됩니다. 오류가 발생할 경우 `errno`는 운영 체제에서 제공되는 오류 특성에 대한 정보에 기반을 둡니다. `errno`에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.  
  
## <a name="remarks"></a>설명  
 `_expand_dbg` 함수는 _[expand](../../c-runtime-library/reference/expand.md) 함수의 디버그 버전입니다. [_DEBUG](../../c-runtime-library/debug.md)를 정의하지 않은 경우 `_expand_dbg`에 대한 각 호출이 `_expand`에 대한 호출로 줄어듭니다. `_expand`와 `_expand_dbg` 둘 다 기본 힙에서 메모리 블록을 크기 조정하지만 `_expand_dbg`는 여러 디버깅 기능을 수용합니다. 이러한 기능에는 메모리 블록의 사용자 부분 한 쪽에서의 버퍼(어느 쪽이든지 상관없이)로 누수 테스트, 블록 형식 매개 변수로 특정 할당 형식 추적 및 `filename`/`linenumber` 정보로 할당 요청의 원점을 확인하는 기능이 있습니다.  
  
 `_expand_dbg`는 요청된 `newSize`보다 약간 더 많은 공간을 사용하여 메모리 블록의 크기를 조정합니다. `newSize`는 원래 할당된 메모리 블록의 크기보다 더 크거나 작을 수 있습니다. 디버그 힙 관리자는 추가 공간을 사용하여 디버그 메모리 블록을 연결하고 응용 프로그램에 디버그 헤더 정보를 제공하고 버퍼를 덮어씁니다. 크기를 조정하려면 원래 메모리 블록을 확장하거나 축소합니다. `_expand_dbg`도 [_realloc_dbg](../../c-runtime-library/reference/realloc-dbg.md) 함수처럼 메모리 블록을 이동하지 않습니다.  
  
 `newSize`가 원래 블록 크기보다 클 경우 메모리 블록이 확장됩니다. 확장 중에 메모리 블록이 요청된 크기를 수용할 만큼 확장될 수 없다면 `NULL`이 반환됩니다. `newSize`가 원래 블록 크기보다 작으면 메모리 블록은 새 크기와 같아질 때까지 축소됩니다.  
  
 기본 힙의 디버그 버전에서 메모리 블록을 할당, 초기화 및 관리하는 방법에 대한 자세한 내용은 [CRT 디버그 힙 정보](/visualstudio/debugger/crt-debug-heap-details)를 참조하세요. 할당 블록 형식과 이러한 형식의 사용 방법에 대한 자세한 내용은 [디버그 힙의 블록 형식](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요. 응용 프로그램의 디버그 빌드에서 표준 힙 함수를 호출하는 것과 해당 함수의 디버그 버전을 호출하는 것의 차이에 대한 자세한 내용은 [힙 할당 함수의 디버그 버전](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)을 참조하세요.  
  
 이 함수는 해당 매개 변수의 유효성을 검사합니다. `memblock`가 null 포인터인 경우 또는 크기가 `_HEAP_MAXREQ`보다 큰 경우 이 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)의 설명대로 잘못된 매개 변수 처리기를 호출합니다. 계속해서 실행하도록 허용된 경우 `errno` 는 `EINVAL` 로 설정되고 함수는 `NULL`을 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`_expand_dbg`|\<crtdbg.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="libraries"></a>라이브러리  
 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)의 디버그 버전만 해당됩니다.  
  
## <a name="example"></a>예  
  
```  
// crt_expand_dbg.c  
//  
// This program allocates a block of memory using _malloc_dbg  
// and then calls _msize_dbg to display the size of that block.  
// Next, it uses _expand_dbg to expand the amount of  
// memory used by the buffer and then calls _msize_dbg again to  
// display the new amount of memory allocated to the buffer.  
//  
  
#include <stdio.h>  
#include <malloc.h>  
#include <stdlib.h>  
#include <crtdbg.h>  
  
int main( void )  
{  
   long *buffer;  
   size_t size;  
  
   // Call _malloc_dbg to include the filename and line number  
   // of our allocation request in the header  
   buffer = (long *)_malloc_dbg( 40 * sizeof(long),  
                                 _NORMAL_BLOCK, __FILE__, __LINE__ );  
   if( buffer == NULL )  
      exit( 1 );  
  
   // Get the size of the buffer by calling _msize_dbg  
   size = _msize_dbg( buffer, _NORMAL_BLOCK );  
   printf( "Size of block after _malloc_dbg of 40 longs: %u\n", size );  
  
   // Expand the buffer using _expand_dbg and show the new size  
   buffer = (long *)_expand_dbg( buffer, size + sizeof(long),  
                                 _NORMAL_BLOCK, __FILE__, __LINE__ );  
  
   if( buffer == NULL )  
      exit( 1 );  
   size = _msize_dbg( buffer, _NORMAL_BLOCK );  
   printf( "Size of block after _expand_dbg of 1 more long: %u\n",  
           size );  
  
   free( buffer );  
   exit( 0 );  
}  
```  
  
```Output  
Size of block after _malloc_dbg of 40 longs: 160  
Size of block after _expand_dbg of 1 more long: 164  
```  
  
## <a name="comment"></a>주석  
 이 프로그램의 출력은 모든 섹션을 확장하는 컴퓨터 기능에 따라 달라집니다. 모든 섹션이 확장되면 출력이 출력 섹션에 반영됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버그 루틴](../../c-runtime-library/debug-routines.md)   
 [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md)