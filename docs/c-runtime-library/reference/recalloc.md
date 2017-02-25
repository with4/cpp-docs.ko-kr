---
title: "_recalloc | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_recalloc"
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
  - "_recalloc"
  - "recalloc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_recalloc 함수"
  - "recalloc 함수"
ms.assetid: 1db8305a-3f03-418c-8844-bf9149f63046
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# _recalloc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`realloc` 및 `calloc`의 조합입니다.  메모리에 배열을 다시 할당 하고 해당 요소를 0으로 초기화 합니다.  
  
## 구문  
  
```  
void *_recalloc(   
   void *memblock  
   size_t num,  
   size_t size   
);  
```  
  
#### 매개 변수  
 `memblock`  
 이전에 할당된 메모리 블록에 대한 포인터입니다.  
  
 `num`  
 요소 수 입니다.  
  
 `size`  
 각 요소의 길이 \(바이트\)입니다.  
  
## 반환 값  
 `_recalloc` 는 메모리 블럭을 재할당\(이동 가능한\) 하기 위해 `void` 포인터를 반환합니다.  
  
 주어진 크기에 대해 확장 가능하고 충분히 사용 가능한 메모리 블록이 있는 경우, 원래 블록은 변경 되지 않고 `NULL` 가 반환됩니다.  
  
 요청된 된 크기가 0 인 경우 `memblock` 가 가르키는 포인터는 해제 됩니다. 반환 값은 `NULL` 이고 `memblock` 는 해제 된 블록을 가르킵니다.  
  
 반환 값은 모든 개체 형식의 저장소가 적절하게 정렬되도록 하는 것을 보증하는 저장 공간을 가리킵니다.  `void`가 아닌 형식에 포인터를 반환하려면 반환 값에 대한 형식 캐스트를 사용합니다.  
  
## 설명  
 `recalloc` 함수는 할당된 메모리 블록의 크기를 변경합니다.  `memblock` 인수는 메모리 블록의 시작 부분을 가리킵니다.  `memblock` 가 `NULL` 인 경우, \_`recalloc` 는 [calloc](../../c-runtime-library/reference/calloc.md) 와 같은 방법으로 작동하고 `num` \* `size` 바이트의 새로운 블록을 할당합니다.  각 요소는 0으로 초기화 됩니다.  `memblock` 가 `NULL` 이 아닌 경우, `calloc`, [malloc](../../c-runtime-library/reference/malloc.md), 또는 [realloc](../../c-runtime-library/reference/realloc.md)의 이전 호출에서 반환하는 포인터입니다.  
  
 새 블럭이 새로운 메모리 위치에 있을 수 있기 때문에, \_`recalloc` 가 반환하는 포인터는 `memblock` 인수로 전달 되는 포인터로 생성 되지 않습니다.  
  
 `_recalloc` 는 메모리 할당이 실패하거나 요청한 메모리 크기가 `_HEAP_MAXREQ`를 초과하는 경우 `errno` 는 `ENOMEM` 로 설정됩니다.  이 오류 코드 및 기타 오류 코드에 대한 자세한 내용은 [errno, \_doserrno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
 `recalloc` 는 새 처리기 모드를 설정하는 C\+\+[\_set\_new\_mode](../../c-runtime-library/reference/set-new-mode.md) 함수를 사용 하기 위해 `realloc` 를 호출합니다.  새 처리기 모드는 실패 시 `realloc`이 [\_set\_new\_handler](../../c-runtime-library/reference/set-new-handler.md)에서 설정한 대로 새 처리기 루틴을 호출하는지 여부를 나타냅니다.  기본적으로 `realloc`은 메모리 할당에 실패한 경우 새 처리기 루틴을 호출하지 않습니다.  `recalloc`이 메모리 할당에 실패하면 `realloc`이 새 처리기 루틴을 `new` 연산자가 같은 이유로 실패할 때와 동일한 방식으로 호출할 수 있도록 기본 동작을 재정의할 수 있습니다.  기본값을 재정의하려면 다음을 호출합니다.  
  
```  
_set_new_mode(1)  
```  
  
 초기 프로그램 또는 NEWMODE.OBJ에 대한 링크.  
  
 응용 프로그램이 C 런타임 라이브러리의 디버그 버전에 연결 되면 `recalloc` 가 [\_recalloc\_dbg](../../c-runtime-library/reference/recalloc-dbg.md) 에 대해 해결됩니다.  디버깅 프로세스를 하는 동안 힙을 관리하는 방법에 대한 자세한 내용은 [CRT 디버그 힙](../Topic/CRT%20Debug%20Heap%20Details.md) 를 참조하십시오.  
  
 `_recalloc`는 `__declspec(noalias)` 및 `__declspec(restrict)`로 표시됩니다. 즉, 함수가 전역 변수를 수정하지 않고 반환된 포인터가 별칭이 지정되지 않도록 보증합니다.  자세한 내용은 [noalias](../../cpp/noalias.md) 및 [restrict](../../cpp/restrict.md) 를 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_recalloc`|\<stdlib.h\> 및 \<malloc.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [메모리 할당](../../c-runtime-library/memory-allocation.md)   
 [\_recalloc\_dbg](../../c-runtime-library/reference/recalloc-dbg.md)   
 [\_aligned\_recalloc](../../c-runtime-library/reference/aligned-recalloc.md)   
 [\_aligned\_offset\_recalloc](../../c-runtime-library/reference/aligned-offset-recalloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [링크 옵션](../../c-runtime-library/link-options.md)