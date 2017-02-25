---
title: "_alloca | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_alloca"
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
  - "_alloca"
  - "alloca"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_alloca 함수"
  - "alloca 함수"
  - "메모리 할당, 스택"
ms.assetid: 74488eb1-b71f-4515-88e1-cdd03b6f8225
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# _alloca
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

스택에 메모리를 할당합니다.  더 안전한 버전을 사용할 수 있기 때문에 이 함수는 더 이상 사용되지 않습니다. [\_malloca](../../c-runtime-library/reference/malloca.md)를 참조하십시오.  
  
## 구문  
  
```  
void *_alloca(   
   size_t size   
);  
```  
  
#### 매개 변수  
 \[in\] `size`  
 스택에서 할당할 바이트 수입니다.  
  
## 반환 값  
 `_alloca` 루틴은 할당된 공간에 대해 개체의 저장소에 대해 적절하게 정렬되는 `void` 포인터를 반환합니다.  `size`이 0인 경우 `_alloca`는 길이가 0인 항목을 할당하고 유효한 포인터를 해당 항목에 반환합니다.  
  
 해당 공간을 할당할 수 없는 경우 스택 오버플로 예외가 생성 됩니다.  스택 오버플로 예외는 C\+\+ 예외가 아닙니다. 구조화 된 예외는 입니다.  C \+\+ 예외 처리를 사용 하는 대신에 [구조적 예외 처리](../../cpp/structured-exception-handling-c-cpp.md) \(SEH\) 을 사용하십시오.  
  
## 설명  
 `_alloca`는 `size` 바이트를 프로그램 스택으로부터 할당합니다.  할당된 공간은 함수 종료가 호출되면 자동으로 해제됩니다. \(단순히 할당 범위 밖으로 지나갈 때가 아니라\)  따라서, `_alloca`에 의해 반환된 포인터 값을 [free](../../c-runtime-library/reference/free.md)의 인수로 전달하지 마십시오.  
  
 예외 처리기\(EH\) 에서 `_alloca` 를 명시적으로 호출하는 것에는 제한이 있습니다.  x86 프로세서에서 실행되는 EH 루틴은 자신의 메모리의 프레임에서 작동합니다 : 바깥 쪽 함수의 스택 포인터의 현재 위치를 기반으로하지 않는 메모리 공간에서 자신의 작업을 수행 할 수 있습니다.  가장 일반적인 구현은 Windows NT 구조적 예외 처리\(SEH\) 및 C\+\+ catch 절 식에 포함됩니다.  그러므로, EH 루틴 호출에 반환하는 동안 발생한 에러 시나리오 중 하나에서의 명시적인 `_alloca` 호출 :  
  
-   Windows NT SEH 예외 필터 식: `__except`\(`_alloca ()` \)  
  
-   Windows NT SEH 마지막 예외 처리기: `__finally` {`_alloca ()` }  
  
-   C\+\+ EH catch clause expression  
  
 그러나 `_alloca`는 EH 루틴이나 이전에 나열 된 EH 시나리오 중 하나에 의해 호출 된 응용 프로그램 지원 콜백에서 직접적으로 호출 될 수 있습니다.  
  
> [!IMPORTANT]
>  Windows XP 에서, `_alloca` 가 try\/catch 블록에서 호출 된 경우, [\_resetstkoflw](../../c-runtime-library/reference/resetstkoflw.md) 를 호출해야 합니다.  
  
 위의 제한을 사용 하는 경우 외에, [\/clr \(공용 언어 런타임 컴파일\)](../../build/reference/clr-common-language-runtime-compilation.md) 옵션을 사용할 때 `_alloca` 는 `__except` 블록에서 사용될 수 없습니다.  자세한 내용은 [\/clr Restrictions](../../build/reference/clr-restrictions.md) 를 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_alloca`|\<malloc.h\>|  
  
## 예제  
  
```  
// crt_alloca.c  
// This program demonstrates the use of  
// _alloca and trapping any exceptions  
// that may occur.  
  
#include <windows.h>  
#include <stdio.h>  
#include <malloc.h>  
  
int main()  
{  
    int     size = 1000;  
    int     errcode = 0;  
    void    *pData = NULL;  
  
    // Note: Do not use try/catch for _alloca,  
    // use __try/__except, since _alloca throws  
    // Structured Exceptions, not C++ exceptions.  
  
    __try {  
        // An unbounded _alloca can easily result in a   
        // stack overflow.  
        // Checking for a size < 1024 bytes is recommended.  
        if (size > 0 && size < 1024)  
        {  
            pData = _alloca( size );  
            printf_s( "Allocated %d bytes of stack at 0x%p",  
                      size, pData);  
        }  
        else  
        {  
            printf_s("Tried to allocate too many bytes.\n");  
        }  
    }  
  
    // If an exception occured with the _alloca function  
    __except( GetExceptionCode() == STATUS_STACK_OVERFLOW )  
    {  
        printf_s("_alloca failed!\n");  
  
        // If the stack overflows, use this function to restore.  
        errcode = _resetstkoflw();  
        if (errcode)  
        {  
            printf_s("Could not reset the stack!\n");  
            _exit(1);  
        }  
    };  
}  
```  
  
  **Allocated 1000 bytes of stack at 0x0012FB50**   
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [메모리 할당](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [\_resetstkoflw](../../c-runtime-library/reference/resetstkoflw.md)   
 [\_malloca](../../c-runtime-library/reference/malloca.md)