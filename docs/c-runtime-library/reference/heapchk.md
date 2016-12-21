---
title: "_heapchk | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_heapchk"
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
  - "_heapchk"
  - "heapchk"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_heapchk 함수"
  - "힙의 일관성 검사"
  - "디버깅[CRT], 힙 관련 문제"
  - "heapchk 함수"
  - "힙, 일관성 검사"
ms.assetid: 859619a5-1e35-4f02-9e09-11d9fa266ec0
caps.latest.revision: 13
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _heapchk
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

힙에서 일관성 검사를 실행합니다.  
  
## 구문  
  
```  
int _heapchk( void );  
```  
  
## 반환 값  
 `_heapchk` 는 Malloc.h에 정의된 다음 정수 매니페스트 상수 중 하나를 반환 합니다.  
  
 `_HEAPBADBEGIN`  
 초기 헤더 정보가 잘못되었거나 초기 헤더 정보를 찾을 수 없습니다.  
  
 `_HEAPBADNODE`  
 잘못된 노드가 발견되었거나 힙이 손상되었습니다.  
  
 `_HEAPBADPTR`  
 힙을 가리키는 포인터가 유효하지 않습니다.  
  
 `_HEAPEMPTY`  
 힙이 초기화되지 않았습니다.  
  
 `_HEAPOK`  
 힙은 일관성 있는 것으로 나타납니다.  
  
 게다가, 오류가 발생 한 경우 `_heapchk` 은 `errno` 를 `ENOSYS`설정합니다.  
  
## 설명  
 `_heapchk` 함수는 힙의 최소한의 일관성을 검사하여 힙 관련 문제의 디버그를 도웁니다.  운영 체제를 지원 하지 않는 경우, `_heapchk`\(예: Windows 98\), 함수는 `_HEAPOK` 을 반환하고 `errno` 를 `ENOSYS` 설정합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|선택적 헤더|  
|--------|-----------|------------|  
|`_heapchk`|\<malloc.h\>|\<\<errno.h\>\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_heapchk.c  
// This program checks the heap for  
// consistency and prints an appropriate message.  
  
#include <malloc.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int  heapstatus;  
   char *buffer;  
  
   // Allocate and deallocate some memory  
   if( (buffer = (char *)malloc( 100 )) != NULL )  
      free( buffer );  
  
   // Check heap status  
   heapstatus = _heapchk();  
   switch( heapstatus )  
   {  
   case _HEAPOK:  
      printf(" OK - heap is fine\n" );  
      break;  
   case _HEAPEMPTY:  
      printf(" OK - heap is empty\n" );  
      break;  
   case _HEAPBADBEGIN:  
      printf( "ERROR - bad start of heap\n" );  
      break;  
   case _HEAPBADNODE:  
      printf( "ERROR - bad node in heap\n" );  
      break;  
   }  
}  
```  
  
  **OK \- 힙이 정상입니다.**   
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [메모리 할당](../../c-runtime-library/memory-allocation.md)   
 [\_heapadd](../../c-runtime-library/heapadd.md)   
 [\_heapmin](../../c-runtime-library/reference/heapmin.md)   
 [\_heapset](../../c-runtime-library/heapset.md)   
 [\_heapwalk](../../c-runtime-library/reference/heapwalk.md)