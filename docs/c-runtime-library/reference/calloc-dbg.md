---
title: "_calloc_dbg | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_calloc_dbg"
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
  - "_calloc_dbg"
  - "calloc_dbg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_calloc_dbg 함수"
  - "calloc_dbg 함수"
ms.assetid: 7f62c42b-eb9f-4de5-87d0-df57036c87de
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# _calloc_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

디버깅 헤더에 대한 추가 공간을 사용하여 힙에서 메모리 블록 수를 할당하고 버퍼를 덮어씁니다\(디버그 버전에만 해당\).  
  
## 구문  
  
```  
void *_calloc_dbg(   
   size_t num,  
   size_t size,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### 매개 변수  
 `num`  
 메모리 블록 수를 요청합니다.  
  
 `size`  
 각 메모리 블록의 크기를 \(바이트\) 요청합니다.  
  
 `blockType`  
 메모리 블록 형식을 요청합니다.  `_CLIENT_BLOCK`  또는  `_NORMAL_BLOCK` .  
  
 할당 블록 종류 및 사용 방법에 대한 더 자세한 내용은  [디버그 힙의 블록 형식](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap)을 참조하십시오.  
  
 `filename`  
 할당 작업 또는 `NULL`을 요청하는 소스 파일의 이름에 대한 포인터입니다.  
  
 `linenumber`  
 할당 작업 요청하는 소스 파일의 줄 번호 또는  `NULL`입니다.  
  
 `filename`  및  `linenumber`  매개 변수는  `_calloc_dbg`  가 명시적으로 호출되거나  [\_CRTDBG\_MAP\_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md) 전처리기 상수가 정의되었을 경우, 사용할 수 있습니다.  
  
## 반환 값  
 성공적으로 완료되면, 이 함수는 새로운 처리기 함수를 호출하는 마지막으로 할당된 메모리 블록의 사용자 영역에 대한 포인터 또는 `NULL`을 반환 합니다.  반환 동작의 완벽한 설명은 설명 부분을 참조하십시오.  새 처리기 함수를 사용하는 방법에 대한 자세한 내용은 [calloc](../../c-runtime-library/reference/calloc.md)함수를 참조하십시오.  
  
## 설명  
 `_calloc_dbg`는 [calloc](../../c-runtime-library/reference/calloc.md) 함수의 디버그 버전입니다.  [\_DEBUG](../../c-runtime-library/debug.md)를 정의 하지 않으면,  `_calloc_dbg` 의 각 호출은  `calloc` 의 호출에 감소됩니다.   `calloc`  및  `_calloc_dbg`  둘다 기본 힙에서  `num`  메모리 블록을 할당하지만  `_calloc_dbg` 는 몇 개의 디버깅 기능을 제공합니다.  
  
-   누수를 테스트하는 블록의 사용자 부분 양쪽의 버퍼입니다.  
  
-   특정한 할당 형식을 추적하는 블록 형식 매개 변수입니다.  
  
-   `filename`\/ `linenumber` 정보는 할당 요청의 출처를 확인합니다.  
  
 `_calloc_dbg`은 요청된  `size` 보다 조금 더 많은 공간을 사용하여 각 메모리 블록을 할당합니다.  추가 공간은 디버그 힙 관리자가 디버그 메모리 블록을 연결하고 디버그 헤더 정보를 사용하여 응용 프로그램을 제공하고 버퍼를 덮어쓰는데 사용됩니다.  블록이 할당 될 때, 사용자의 블록 부분은 0xCD 값으로 채워지고 덮어쓰기 각 버퍼들은 0xFD로 채워집니다.  
  
 메모리 할당이 실패할 경우, `_calloc_dbg`은  `errno`  를  `ENOMEM` 로 설정합니다. 앞에서 설명한 오버 헤드 등 필요한 메모리 양이 `_HEAP_MAXREQ`를 초과하는 경우엔  `EINVAL` 가 반환됩니다.  이 오류 코드 및 기타 오류 코드에 대한 자세한 내용은 [errno, \_doserrno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
 기본 힙의 디버그 버전에서 메모리 블록이 어떻게 할당되고 초기화되고 관리되는지에 대한 자세한 내용은 [CRT 디버그 힙 정보](../Topic/CRT%20Debug%20Heap%20Details.md) 를 참조하십시오.  호출 표준 힙 함수와 비교해 응용 프로그램의 디버그 빌드에서 디버그 버전의 차이점에 대한 내용은 [힙 할당 함수의 디버그 버전](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md)를 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_calloc_dbg`|\<crtdbg.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_callocd.c  
/*  
 * This program uses _calloc_dbg to allocate space for  
 * 40 long integers. It initializes each element to zero.  
 */  
#include <stdio.h>  
#include <malloc.h>  
#include <crtdbg.h>  
  
int main( void )  
{  
        long *bufferN, *bufferC;  
  
        /*   
         * Call _calloc_dbg to include the filename and line number  
         * of our allocation request in the header and also so we can  
         * allocate CLIENT type blocks specifically  
         */  
        bufferN = (long *)_calloc_dbg( 40, sizeof(long), _NORMAL_BLOCK, __FILE__, __LINE__ );  
        bufferC = (long *)_calloc_dbg( 40, sizeof(long), _CLIENT_BLOCK, __FILE__, __LINE__ );  
        if( bufferN != NULL && bufferC != NULL )  
              printf( "Allocated memory successfully\n" );  
        else  
              printf( "Problem allocating memory\n" );  
  
        /*   
         * _free_dbg must be called to free CLIENT type blocks  
         */  
        free( bufferN );  
        _free_dbg( bufferC, _CLIENT_BLOCK );  
}  
```  
  
  **성공적으로 할당 된 메모리**   
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [디버그 루틴](../../c-runtime-library/debug-routines.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md)   
 [\_DEBUG](../../c-runtime-library/debug.md)