---
title: "_expand | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_expand"
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
  - "_bexpand"
  - "fexpand"
  - "expand"
  - "nexpand"
  - "_fexpand"
  - "_nexpand"
  - "bexpand"
  - "_expand"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_expand 함수"
  - "expand 함수"
  - "메모리 블록, 크기 변경"
ms.assetid: 4ac55410-39c8-45c7-bccd-3f1042ae2ed3
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# _expand
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

메모리 블록의 크기를 변경합니다.  
  
## 구문  
  
```  
void *_expand(   
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
 `_expand`는 재할당된 메모리 블록에 대한 void 포인터를 반환합니다.  `realloc`과는 달리, `_expand`는 블록의 크기를 변경하기 위해 블록을 이동시킬 수 없습니다.  따라서, 블럭을 이동하지 않고 확장하기에 충분한 메모리가 존재하는 경우, `memblock` 매개 변수의 `_expand`는 반환 값과 같습니다.  
  
 `_expand`는 작업 동안 오류가 발견된 경우 `NULL`을 반환합니다.  예를 들어, `_expand`이 메모리 블록을 축소시키는 데에 사용된 경우, 작은 블록 힙 또는 잘못된 블록 포인터에서 손상을 발견하고 `NULL`을 반환할 수 있습니다.  
  
 블록을 움직이지 않고 주어진 크기로 확장할 메모리가 충분하지 않은 경우, 이 함수는 `NULL`을 반환합니다.  `_expand`는 요청된 것보다 작은 크기로 확장된 블록을 반환하지 않습니다.  `errno`는 오류 발생시 실패의 특성을 나타냅니다.  `errno`에 대한 자세한 내용은 [errno, \_doserrno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
 반환 값은 모든 개체 형식의 저장소가 적절하게 정렬되도록 하는 것을 보증하는 저장 공간을 가리킵니다.  새 항목의 크기를 확인하려면 `_msize`를 사용합니다.  `void`가 아닌 형식에 포인터를 반환하려면 반환 값에 대한 형식 캐스트를 사용합니다.  
  
## 설명  
 `_expand` 함수는 힙에서 위치를 이동시키지 않고 블록을 축소하거나 확장하여 이전에 할당된 메모리 블록의 크기를 변경합니다.  `memblock` 매개 변수는 블록의 시작 부분을 가리킵니다.  `size` 매개 변수는 블록의 새 크기를 바이트 단위로 제공합니다.  블록의 내용은 새 크기가 기존보다 짧아질 때까지 변경되지 않습니다.  `memblock`는 해제된 블록이 되어서는 안됩니다.  
  
> [!NOTE]
>  64 비트 플랫폼에서, `_expand`는 새 크기가 현재 크기보다 작으면 블록을 축소하지 않을 수 있습니다. 특히, 블록이 16K보다 크기가 작아서 낮은 조각화 힙 영역에 할당되었다면, `_expand`는 블록을 변경하지 않고 `memblock`을 반환합니다.  
  
 응용 프로그램이 C 런타임 라이브러리의 디버그 버전에 연결되면 `_expand`은 [\_expand\_dbg](../../c-runtime-library/reference/expand-dbg.md)가 됩니다.  디버깅 프로세스를 하는 동안 힙을 관리하는 방법에 대한 자세한 내용은 [CRT 디버그 힙](../Topic/CRT%20Debug%20Heap%20Details.md) 를 참조하십시오.  
  
 이 함수는 해당 매개 변수의 유효성을 검사합니다.   `memblock` 이 null 포인터인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 함수는 잘못된 매개 변수 처리기를 호출합니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 `errno` 를 `EINVAL` 로 설정하고 `NULL`을 반환합니다.  `size`가 `_HEAP_MAXREQ`보다 큰 경우, `errno`는 `ENOMEM`로 설정되며 함수는 `NULL`을 반환합니다.  
  
## 요구 사항  
  
|Function|필수 헤더|  
|--------------|-----------|  
|`_expand`|\<malloc.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_expand.c  
  
#include <stdio.h>  
#include <malloc.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   char *bufchar;  
   printf( "Allocate a 512 element buffer\n" );  
   if( (bufchar = (char *)calloc( 512, sizeof( char ) )) == NULL )  
      exit( 1 );  
   printf( "Allocated %d bytes at %Fp\n",   
         _msize( bufchar ), (void *)bufchar );  
   if( (bufchar = (char *)_expand( bufchar, 1024 )) == NULL )  
      printf( "Can't expand" );  
   else  
      printf( "Expanded block to %d bytes at %Fp\n",   
            _msize( bufchar ), (void *)bufchar );  
   // Free memory   
   free( bufchar );  
   exit( 0 );  
}  
```  
  
  **512 요소 버퍼를 할당합니다.**  
**002C12BC에 512 바이트가 할당되었습니다.**  
**002C12BC에서 1024 바이트로 블록이 확장되었습니다.**   
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [메모리 할당](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [\_msize](../../c-runtime-library/reference/msize.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)