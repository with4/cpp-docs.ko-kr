---
title: "calloc | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "calloc"
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
  - "calloc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "메모리 할당, 배열"
  - "calloc 함수"
ms.assetid: 17bb79a1-98cf-4096-90cb-1f9365cd6829
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# calloc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

요소는 0으로 초기화 된 메모리에 배열을 할당 합니다.  
  
## 구문  
  
```  
void *calloc(   
   size_t num,  
   size_t size   
);  
```  
  
#### 매개 변수  
 `num`  
 요소 수 입니다.  
  
 `size`  
 각 요소의 길이 \(바이트\)입니다.  
  
## 반환 값  
 `calloc` 는 할당 된 공간에 대한 포인터를 반환합니다.  반환 값이 가르키는 저장 공간은 개체의 형식의 저장소에 대해 적절히 정렬 되도록 생성됩니다.  `void`가 아닌 형식에 포인터를 반환하려면 반환 값에 대한 형식 캐스트를 사용합니다.  
  
## 설명  
 `calloc` 함수는 `size` 바이트 길이의 각각인 `num` 요소의 배열에 대해 저장 공간을 할당합니다.  각 요소는 0으로 초기화 됩니다.  
  
 `calloc`는 메모리 할당이 실패하거나 요청한 메모리 크기가 `_HEAP_MAXREQ`를 초과하는 경우 `errno`는 `ENOMEM`로 설정됩니다.  이 오류 코드 및 기타 오류 코드에 대한 자세한 내용은 [errno, \_doserrno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
 `calloc` 는 새 처리기 모드를 설정하는 C\+\+[\_set\_new\_mode](../../c-runtime-library/reference/set-new-mode.md) 함수를 사용 하기 위해 `malloc` 를 호출합니다.  새 처리기 모드는 실패 시 `malloc`이 [\_set\_new\_handler](../../c-runtime-library/reference/set-new-handler.md)에서 설정한 대로 새 처리기 루틴을 호출하는지 여부를 나타냅니다.  기본적으로 `malloc`은 메모리 할당에 실패한 경우 새 처리기 루틴을 호출하지 않습니다.  `calloc`이 메모리 할당에 실패하면 `malloc`이 새 처리기 루틴을 `new` 연산자가 같은 이유로 실패할 때와 동일한 방식으로 호출할 수 있도록 기본 동작을 재정의할 수 있습니다.  기본값을 재정의하려면 다음을 호출합니다.  
  
```  
_set_new_mode(1)  
```  
  
 초기 프로그램 또는 NEWMODE.OBJ에 대한 링크\([링크 옵션](../../c-runtime-library/link-options.md) 참조\).  
  
 응용 프로그램이 C 런타임 라이브러리의 디버그 버전에 연결되면 `calloc`은 [\_calloc\_dbg](../../c-runtime-library/reference/calloc-dbg.md)가 됩니다.  디버깅 프로세스를 하는 동안 힙을 관리하는 방법에 대한 자세한 내용은 [CRT 디버그 힙](../Topic/CRT%20Debug%20Heap%20Details.md) 를 참조하십시오.  
  
 `calloc`는 `__declspec(noalias)` 및 `__declspec(restrict)`로 표시됩니다. 즉, 함수가 전역 변수를 수정하지 않고 반환된 포인터가 별칭이 지정되지 않도록 보증합니다.  자세한 내용은 [noalias](../../cpp/noalias.md) 및 [restrict](../../cpp/restrict.md) 를 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`calloc`|\<stdlib.h\> 및 \<malloc.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_calloc.c  
// This program uses calloc to allocate space for  
// 40 long integers. It initializes each element to zero.  
  
#include <stdio.h>  
#include <malloc.h>  
  
int main( void )  
{  
   long *buffer;  
  
   buffer = (long *)calloc( 40, sizeof( long ) );  
   if( buffer != NULL )  
      printf( "Allocated 40 long integers\n" );  
   else  
      printf( "Can't allocate memory\n" );  
   free( buffer );  
}  
```  
  
  **Allocated 40 long integers**   
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [메모리 할당](../../c-runtime-library/memory-allocation.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)