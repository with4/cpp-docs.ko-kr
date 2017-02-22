---
title: "realloc | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "realloc"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-heap-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_brealloc"
  - "_nrealloc"
  - "realloc"
  - "_frealloc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_brealloc 함수"
  - "realloc 함수"
  - "nrealloc 함수"
  - "frealloc 함수"
  - "_nrealloc 함수"
  - "메모리 블록, 다시 할당"
  - "메모리, 다시 할당"
  - "_frealloc 함수"
  - "메모리 블록 다시 할당"
ms.assetid: 2b2239de-810b-4b11-9438-32ab0a244185
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# realloc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

메모리 블록 다시 할당  
  
## 구문  
  
```  
void *realloc(  
   void *memblock,  
   size_t size   
);  
```  
  
#### 매개 변수  
 `memblock`  
 이전에 할당된 메모리 블록에 대한 포인터입니다.  
  
 `size`  
 새 크기\(바이트로\)입니다.  
  
## 반환 값  
 `realloc` 는 메모리 블럭을 재할당\(이동 가능한\) 하기 위해 `void` 포인터를 반환합니다.  
  
 주어진 크기에 대해 확장 가능하고 충분히 사용 가능한 메모리 블록이 있는 경우, 원래 블록은 변경 되지 않고 `NULL` 가 반환됩니다.  
  
 `size`가 0 인 경우 `memblock` 가 가르키는 포인터는 해제 됩니다. 반환 값은 `NULL` 이고 `memblock` 는 해제 된 블록을 가르킵니다.  
  
 반환 값은 모든 개체 형식의 저장소가 적절하게 정렬되도록 하는 것을 보증하는 저장 공간을 가리킵니다.  `void`가 아닌 형식에 포인터를 반환하려면 반환 값에 대한 형식 캐스트를 사용합니다.  
  
## 설명  
 \_`realloc` 함수는 할당된 메모리 블록의 크기를 변경합니다.  `memblock` 인수는 메모리 블록의 시작 부분을 가리킵니다.  `memblock` 가 `NULL` 인 경우, `realloc` 는 `size` 바이트의 새로운 블록을 할당하고 `malloc` 와 같은 방법으로 작동합니다.  `memblock` 가 `NULL` 이 아닌 경우, `calloc`, `malloc`, 또는 `realloc`의 이전 호출에서 반환하는 포인터입니다.  
  
 `size` 인수는 블록의 새 크기를 바이트 단위로 제공합니다.  새로운 블록이 다른 위치에있을 수 있지만, 블록의 내용은 새롭고 오래된 크기 중 짧은것으로 변하지 않습니다.  새 블럭이 새로운 메모리 위치에 있을 수 있기 때문에, \_`realloc` 가 반환하는 포인터는 `memblock` 인수로 전달 되는 포인터로 생성 되지 않습니다.  `realloc` 는 버퍼 증가의 경우 메모리에 새로 할당 된 0이 아닙니다.  
  
 `realloc` 는 메모리 할당이 실패하거나 요청한 메모리 크기가 `_HEAP_MAXREQ`를 초과하는 경우 `errno` 는 `ENOMEM` 로 설정됩니다.  이 오류 코드 및 기타 오류 코드에 대한 자세한 내용은 [errno, \_doserrno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
 `realloc`  는 새 처리 모드를 설정하기 위한 C\+\+ [\_set\_new\_mode](../../c-runtime-library/reference/set-new-mode.md) 함수를 사용하기 위해 `malloc` 를 호출합니다.  새 처리기 모드는 실패 시 `malloc`이 [\_set\_new\_handler](../../c-runtime-library/reference/set-new-handler.md)에서 설정한 대로 새 처리기 루틴을 호출하는지 여부를 나타냅니다.  기본적으로 `malloc`은 메모리 할당에 실패한 경우 새 처리기 루틴을 호출하지 않습니다.  `realloc`이 메모리 할당에 실패하면 `malloc`이 새 처리기 루틴을 `new` 연산자가 같은 이유로 실패할 때와 동일한 방식으로 호출할 수 있도록 기본 동작을 재정의할 수 있습니다.  기본값을 재정의하려면 다음을 호출합니다.  
  
```  
_set_new_mode(1)  
```  
  
 초기 프로그램 또는 NEWMODE.OBJ에 대한 링크\([링크 옵션](../../c-runtime-library/link-options.md) 참조\).  
  
 응용 프로그램이 C 런타임 라이브러리의 디버그 버전에 연결되면 `realloc`은 [\_realloc\_dbg](../../c-runtime-library/reference/realloc-dbg.md)가 됩니다.  디버깅 프로세스를 하는 동안 힙을 관리하는 방법에 대한 자세한 내용은 [CRT 디버그 힙](../Topic/CRT%20Debug%20Heap%20Details.md) 를 참조하십시오.  
  
 `realloc`는 `__declspec(noalias)` 및 `__declspec(restrict)`로 표시됩니다. 즉, 함수가 전역 변수를 수정하지 않고 반환된 포인터가 별칭이 지정되지 않도록 보증합니다.  자세한 내용은 [noalias](../../cpp/noalias.md) 및 [restrict](../../cpp/restrict.md) 를 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`realloc`|\<stdlib.h\> 및 \<malloc.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
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
  
  **Size of block after malloc of 1000 longs: 4000**  
**Size of block after realloc of 1000 more longs: 8000**   
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [메모리 할당](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)