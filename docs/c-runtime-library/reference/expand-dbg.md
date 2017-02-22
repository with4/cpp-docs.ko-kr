---
title: "_expand_dbg | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_expand_dbg"
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
apitype: "DLLExport"
f1_keywords: 
  - "expand_dbg"
  - "_expand_dbg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "메모리 블록, 크기 변경"
  - "expand_dbg 함수"
  - "_expand_dbg 함수"
ms.assetid: dc58c91f-72a8-48c6-b643-fe130fb6c1fd
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# _expand_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

블록을 확장 또는 축소하여 힙 메모리에 지정된 블록 크기 조정합니다. \(디버그 버전에만 해당\)  
  
## 구문  
  
```  
void *_expand_dbg(   
   void *userData,  
   size_t newSize,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### 매개 변수  
 `userData`  
 이전에 할당 된 메모리 블록에 대 한 포인터입니다.  
  
 `newSize`  
 블록 \(바이트 단위\)의 새로운 크기를 다시 요청합니다.  
  
 `blockType`  
 크기가 조정된 블록의 형식을 요청합니다:  `_CLIENT_BLOCK` 또는  `_NORMAL_BLOCK` .  
  
 `filename`  
 `NULL` 또는 확장 작업을 요청하는 소스 파일의 이름에 대한 포인터입니다.  
  
 `linenumber`  
 확장 작업 요청하는 소스 파일의 줄 번호 또는 `NULL`입니다.  
  
 `filename`  및  `linenumber`  매개 변수는  `_expand_dbg`  가 명시적으로 호출되거나  [\_CRTDBG\_MAP\_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md) 전처리기 상수가 정의되었을 경우, 사용할 수 있습니다.  
  
## 반환 값  
 성공적으로 완료하면,  `_expand_dbg` 는 리사이즈된 메모리 블록에 대한 포인터를 반환합니다.  메모리를 이동하지 않으므로 주소는 해당 사용자데이터처럼 같습니다.  오류가 발생 하거나 블록이 요청된 크기만큼 확장할 수 없을 경우,  `NULL` 을 반환합니다.  오류가 발생 하면  `errno` 는 실패의 본질에 대한 운영 체제의 정보를 사용합니다.  `errno`에 대한 자세한 내용은 [errno, \_doserrno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
## 설명  
 `_expand_dbg` 함수는 \_[확장](../../c-runtime-library/reference/expand.md) 함수의 디버그 버전입니다.  [\_DEBUG](../../c-runtime-library/debug.md)를 정의 하지 않으면,  `_expand_dbg` 의 각 호출은  `_expand` 의 호출에 감소됩니다.   `_expand`  및  `_expand_dbg` 는 모두 기본 힙에서 블록 메모리를 리사이즈하지만  `_expand_dbg` 은 몇 개의 디버깅 기능을 수용합니다: 특정 유형의 할당을 추적하는 누출 블록 타입 파라미터를 테스트하는 블록의 사용자 부분의 양쪽에 버퍼 및  할당 요청의 출처를 확인하기 위한  `filename` \/ `linenumber`  정보.  
  
 `_expand_dbg`은 요청된  `newSize` 보다 조금 더 많은 공간을 사용하여 지정된 메모리 블록을 리사이즈합니다.  `newSize`는 원래 할당된 메모리 블록의 크기보다 작거나 클 수 있습니다.  추가 공간은 디버그 힙 관리자가 디버그 메모리 블록을 연결하고 디버그 헤더 정보를 사용하여 응용 프로그램을 제공하고 버퍼를 덮어쓰는데 사용됩니다.  크기 조정은 원래 메모리 블록을 축소 하거나 확장하여 수행됩니다.  `_expand_dbg`은 [\_realloc\_dbg](../../c-runtime-library/reference/realloc-dbg.md) 함수와 마찬가지로 메모리 블록을 이동하지 않습니다.  
  
 `newSize` 가 원래 블록 크기보다 클 떄, 메모리 블록을 확장합니다.  확장 하는 동안 , 메모리 블록의 요청 된 크기에 맞게 확장할 수 없는 경우에  `NULL` 이 반환됩니다.   `newSize` 가 원본 블록 크기보다 작을 때,  메모리 블록은 새로운 크기를 얻을 때까지 수축됩니다.  
  
 기본 힙의 디버그 버전에서 메모리 블록이 어떻게 할당되고 초기화되고 관리되는지에 대한 자세한 내용은 [CRT 디버그 힙 정보](../Topic/CRT%20Debug%20Heap%20Details.md) 를 참조하십시오.  할당 블록 종류 및 사용 방법에 대한 더 자세한 내용은  [디버그 힙의 블록 형식](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap)을 참조하십시오.  호출 표준 힙 함수 및 응용 프로그램의 디버그 빌드에서 디버그 버전의 차이점에 대한 내용은 [힙 할당 함수의 디버그 버전](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md)를 참조하십시오.  
  
 이 함수는 해당 매개 변수의 유효성을 검사합니다.   `memblock` 이 null 포인터이거나  `_HEAP_MAXREQ` 보다 크기가 큰 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명 된 대로 이 함수는 잘못 된 매개 변수 처리기를 호출합니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 `errno` 를 `EINVAL` 로 설정하고 `NULL`을 반환합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_expand_dbg`|\<crtdbg.h\>|  
  
 호환성 정보에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 라이브러리  
 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md) 의 유일한 디버그 버전입니다.  
  
## 예제  
  
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
  
  **40 Longs \_malloc\_dbg 이후 블록의 크기: 160**  
**1 더 긴 \_expand\_dbg 이후 블록 크기: 164**   
## 주석  
 이 프로그램의 출력을 컴퓨터의 모든 섹션을 확장하는 능력에 따라 달라집니다.  모든 섹션이 확장 되어 있으면 출력은 출력 섹션에 반영됩니다.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [디버그 루틴](../../c-runtime-library/debug-routines.md)   
 [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md)