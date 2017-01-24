---
title: "_set_new_handler | Microsoft Docs"
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
  - "_set_new_handler"
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
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_set_new_handler"
  - "set_new_handler"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_set_new_handler 함수"
  - "오류 처리"
  - "set_new_handler 함수"
  - "오류 처리기로 제어 전달"
ms.assetid: 1d1781b6-5cf8-486a-b430-f365e0bb023f
caps.latest.revision: 17
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _set_new_handler
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`new` 연잔자가 메모리 할당에 실패하는 경우, 전달자는 오류 처리 메커니즘을 제어합니다.  
  
## 구문  
  
```  
_PNH _set_new_handler(  
   _PNH pNewHandler   
);  
```  
  
#### 매개 변수  
 `pNewHandler`  
 응용 프로그램에서 제공한 메모리 처리 함수 포인터입니다.  0 의 인수는 제거되기 위해 새 처리기를 호출합니다.  
  
## 반환 값  
 `_set_new_handler` 가 등록한 이전의 예외 핸들링 함수를 가르키는 포인터를 반환합니다. 그러므로 이전 함수는 이후에 복원될 수 있습니다.  이전 함수가 설정되어 있지 않은 경우, 반환 값은 기본 기능을 복원하는데 사용 될 수 있습니다 이 값은 `NULL` 일 수 있습니다.  
  
## 설명  
 C\+\+ `_set_new_handler` 함수는 `new` 연산자가 메모리 할당에 실패할 경우 얻어지는 컨트롤 예외 처리 함수를 지정합니다.  `new` 가 실패한 경우, 런타임 시스템은 자동적으로 `_set_new_handler` 에 인수로 전달 되는 예외 처리 함수를 호출합니다.  New.h 에 지정 된 `_PNH` 는 `int` 형을 반환하고 `size_t` 형을 인수로 받는 함수를 가르키는 포인터 입니다.  `size_t` 를 사용하여 할당된 공간의 크기를 지정합니다.  
  
 기본 처리기가 없습니다.  
  
 `_set_new_handler`는 기본적으로 가비지 수집기 스키마입니다.  런타임 시스템은 함수가 0이 아닌 값을 반환할 때마다 다시 시도하고 함수가 0을 반환할 경우 실패합니다.  
  
 프로그램 `_set_new_handler` 함수의 발생은 런타임 시스템 인수 목록에서 지정된 예외 처리 함수를 등록  
  
```  
#include <new.h>  
int handle_program_memory_depletion( size_t )  
{  
   // Your code  
}  
int main( void )  
{  
   _set_new_handler( handle_program_memory_depletion );  
   int *pi = new int[BIG_NUMBER];  
}  
```  
  
 `_set_new_handler` 함수에 전달 된 마지막 함수의 주소를 저장하고 나중에 취소 할 수 있습니다.  
  
```  
_PNH old_handler = _set_new_handler( my_handler );  
   // Code that requires my_handler  
   _set_new_handler( old_handler )  
   // Code that requires old_handler  
```  
  
 C\+\+ [\_set\_new\_mode](../../c-runtime-library/reference/set-new-mode.md) 함수는 [malloc](../../c-runtime-library/reference/malloc.md) 에 대해 새로운 처리기 모드를 설정합니다.  새 처리기 모드는 실패시 `malloc` 이 `_set_new_handler` 에서 설정한 대로 새 처리기 루틴을 호출하는지 여부를 나타냅니다.  기본적으로 `malloc`은 메모리 할당에 실패한 경우 새 처리기 루틴을 호출하지 않습니다.  `malloc`이 메모리 할당에 실패하면 `malloc`이 새 처리기 루틴을 `new` 연산자가 같은 이유로 실패할 때와 동일한 방식으로 호출할 수 있도록 기본 동작을 재정의할 수 있습니다.  기본값을 재정의하려면 다음을 호출합니다.  
  
```  
_set_new_mode(1)  
```  
  
 초기 프로그램 또는 Newmode.obj에 대한 링크\( 참조\).  
  
 사용자 정의 `operator new` 가 제공된 경우, 새 처리기 함수는 실패시 자동적으로 호출 되지 않습니다.  
  
 자세한 내용은 *C\+\+ Language Reference* 의 [new](../../cpp/new-operator-cpp.md) and [delete](../../cpp/delete-operator-cpp.md) 를 참조하십시오.  
  
 이것은 동적으로 링크된 DLL 또는 실행파일에 대한 단일 `_set_new_handler` 처리기 입니다. `_set_new_handler` 를 호출하는 경우에도 처리기는 다른 DLL 또는 실행 파일을 설정하는 처리기를 대체하는 다른 처리기로 바뀔 수 있습니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_set_new_handler`|\<new.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
 이 예제에서는 할당이 실패 하면 MyNewHandler로 제어가 전달 됩니다.  MyNewHandler에 전달 된 인수는 요청 된 바이트 수입니다.  MyNewHandler에서 반환 된 값은 할당을 다시 시도해야 하는지 여부를 나타내는 플래그입니다: 0이 아닌 값을 할당 해야 시도 하고 0 값은 할당에 실패 했음을 나타냅니다.  
  
```  
// crt_set_new_handler.cpp  
// compile with: /c  
#include <stdio.h>  
#include <new.h>  
#define BIG_NUMBER 0x1fffffff  
  
int coalesced = 0;  
  
int CoalesceHeap()  
{  
   coalesced = 1;  // Flag RecurseAlloc to stop   
   // do some work to free memory  
   return 0;  
}  
// Define a function to be called if new fails to allocate memory.  
int MyNewHandler( size_t size )  
{  
   printf("Allocation failed. Coalescing heap.\n");  
  
   // Call a function to recover some heap space.  
   return CoalesceHeap();  
}  
  
int RecurseAlloc() {  
   int *pi = new int[BIG_NUMBER];  
   if (!coalesced)  
      RecurseAlloc();  
   return 0;  
}  
  
int main()  
{  
   // Set the failure handler for new to be MyNewHandler.  
   _set_new_handler( MyNewHandler );  
   RecurseAlloc();  
}  
```  
  
  **할당 하지 못했습니다.  힙 결합입니다.**  
**다음과 같은 메시지가 표시되었습니다. "이 응용 프로그램에서 비정상적인 종료를 런타임에 요청했습니다."**  
**자세한 내용은 해당 응용 프로그램의 지원 팀에 문의하십시오.**    
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [메모리 할당](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)