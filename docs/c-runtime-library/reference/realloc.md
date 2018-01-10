---
title: realloc | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: realloc
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
- _brealloc
- _nrealloc
- realloc
- _frealloc
dev_langs: C++
helpviewer_keywords:
- _brealloc function
- realloc function
- nrealloc function
- frealloc function
- _nrealloc function
- memory blocks, reallocating
- memory, reallocating
- _frealloc function
- reallocate memory blocks
ms.assetid: 2b2239de-810b-4b11-9438-32ab0a244185
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 525b0f0877471b5bfd6d9fa16551b21908f229a6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="realloc"></a>realloc
메모리 블록을 다시 할당합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void *realloc(  
   void *memblock,  
   size_t size   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `memblock`  
 이전에 할당된 메모리 블록에 대한 포인터입니다.  
  
 `size`  
 새 크기(바이트)입니다.  
  
## <a name="return-value"></a>반환 값  
 `realloc`는 다시 할당된(그리고 이동되었을 수 있는) 메모리 블록에 대한 `void` 포인터를 반환합니다.  
  
 블록을 지정된 크기로 확장하는 데 사용할 수 있는 충분한 메모리가 없으면 원래 블록은 변경되지 않고 그대로 유지되며 `NULL`이 반환됩니다.  
  
 `size`가 0이면 `memblock`에서 가리키는 블록이 해제됩니다. 반환 값은 `NULL`이며, `memblock`은 해제된 블록을 가리키는 상태로 유지됩니다.  
  
 반환 값은 모든 형식의 개체 저장을 위해 적절하게 맞도록 보장되어 있는 저장소 공간을 가리킵니다. `void`가 아닌 형식의 포인터를 가져오려면 반환 값에 형식 캐스팅을 사용합니다.  
  
## <a name="remarks"></a>설명  
 `realloc` 함수는 할당된 메모리 블록의 크기를 변경합니다. `memblock` 인수는 메모리 블록의 시작 부분을 가리킵니다. `memblock`이 `NULL`이면 `realloc`는 `malloc`와 같은 방식으로 동작하며 `size`바이트의 새 블록을 할당합니다. `memblock`은 `NULL`이 아닌 경우 `calloc`, `malloc` 또는 `realloc`에 대한 이전 호출에서 반환된 포인터여야 합니다.  
  
 `size` 인수는 블록의 새 크기(바이트)를 제공합니다. 블록의 내용은 새 크기와 이전 크기 중 더 짧은 쪽까지는 변경되지 않습니다. 그러나 새 블록은 다른 위치에 있을 수 있습니다. 새 블록은 새 메모리 위치에 있을 수 있으므로, `realloc`에서 반환하는 포인터가 `memblock` 인수를 통해 전달되는 포인터임이 보장되지 않습니다. `realloc`는 버퍼가 증가해도 새로 할당된 메모리를 비우지 않습니다.  
  
 메모리 할당이 실패하거나 요청된 메모리의 양이 `_HEAP_MAXREQ`를 초과하는 경우 `realloc`는 `errno`를 `ENOMEM`으로 설정합니다. 이 오류 코드 및 기타 오류 코드에 대한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.  
  
 `realloc`는 C++ [_set_new_mode](../../c-runtime-library/reference/set-new-mode.md) 함수를 사용하여 새 처리기 모드를 설정하기 위해 `malloc`를 호출합니다. 새 처리기 모드는 실패 시 `malloc`가 [_set_new_handler](../../c-runtime-library/reference/set-new-handler.md)에서 설정한 대로 새 처리기 루틴을 호출하는지를 나타냅니다. 기본적으로 `malloc`는 메모리 할당 실패 시 새 처리기 루틴을 호출하지 않습니다. `realloc`가 메모리 할당에 실패한 경우 `malloc`이 `new` 연산자가 같은 이유로 실패했을 때 수행하는 것과 동일한 방식으로 새 처리기 루틴을 호출하도록 이 기본 동작을 재정의할 수 있습니다. 기본값을 재정의하려면 다음을  
  
```  
_set_new_mode(1)  
```  
  
 프로그램에서 초기에 호출하거나, NEWMODE.OBJ를 사용하여 연결합니다([링크 옵션](../../c-runtime-library/link-options.md) 참조).  
  
 응용 프로그램이 디버그 버전의 C 런타임 라이브러리에 연결되면 `realloc`는 [_recalloc_dbg](../../c-runtime-library/reference/realloc-dbg.md)가 됩니다. 디버깅 프로세스 동안 힙을 관리하는 방법에 대한 자세한 내용은 [CRT 디버그 힙](/visualstudio/debugger/crt-debug-heap-details)을 참조하세요.  
  
 `realloc`는 `__declspec(noalias)` 및 `__declspec(restrict)`로 표시되며, 이는 함수가 전역 변수를 수정할 수 없도록 보장되고 반환된 포인터에 별칭이 지정되지 않음을 의미합니다. 자세한 내용은 [noalias](../../cpp/noalias.md) 및 [restrict](../../cpp/restrict.md)를 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`realloc`|\<stdlib.h> 및 \<malloc.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## <a name="example"></a>예  
  
```  
// crt_realloc.c  
// This program allocates a block of memory for  
// buffer and then uses _msize to display the size of that  
// block. Next, it uses realloc to expand the amount of  
// memory used by buffer and then calls _msize again to  
// display the new amount of memory allocated to buffer.  
  
#include <stdio.h>  
#include <malloc.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   long *buffer, *oldbuffer;  
   size_t size;  
  
   if( (buffer = (long *)malloc( 1000 * sizeof( long ) )) == NULL )  
      exit( 1 );  
  
   size = _msize( buffer );  
   printf_s( "Size of block after malloc of 1000 longs: %u\n", size );  
  
   // Reallocate and show new size:  
   oldbuffer = buffer;     // save pointer in case realloc fails  
   if( (buffer = realloc( buffer, size + (1000 * sizeof( long )) ))   
        ==  NULL )  
   {  
      free( oldbuffer );  // free original block  
      exit( 1 );  
   }  
   size = _msize( buffer );  
   printf_s( "Size of block after realloc of 1000 more longs: %u\n",   
            size );  
  
   free( buffer );  
   exit( 0 );  
}  
```  
  
```Output  
Size of block after malloc of 1000 longs: 4000  
Size of block after realloc of 1000 more longs: 8000  
```  
  
## <a name="see-also"></a>참고 항목  
 [메모리 할당](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)