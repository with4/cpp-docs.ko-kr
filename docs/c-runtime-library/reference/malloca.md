---
title: "_malloca | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_malloca"
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
  - "malloca"
  - "_malloca"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_malloca 함수"
  - "malloca 함수"
  - "메모리 할당, 스택"
ms.assetid: 293992df-cfca-4bc9-b313-0a733a6bb936
caps.latest.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 27
---
# _malloca
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

스택에 메모리를 할당합니다.  [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md) 에 설명된 대로 이 버전은 보안 향상 기능이 포함된 [\_alloca](../../c-runtime-library/reference/alloca.md) 버전입니다.  
  
## 구문  
  
```  
void *_malloca(   
   size_t size   
);  
```  
  
#### 매개 변수  
 `size`  
 스택에서 할당할 바이트 수입니다.  
  
## 반환 값  
 `_malloca` 루틴은 할당된 공간에 대해 개체의 저장소에 대해 적절하게 정렬되는`void` 포인터를 반환합니다.  `size`이 0인 경우 `_malloca`는  길이가 0인 항목을 할당하고 유효한 포인터를 해당 항목에 반환합니다.  
  
 해당 공간을 할당할 수 없는 경우 스택 오버플로 예외가 생성 됩니다.  스택 오버플로 예외는 C\+\+ 예외가 아닙니다. 구조화 된 예외는 입니다.  C \+\+ 예외 처리를 사용 하는 대신에 [구조적 예외 처리](../../cpp/structured-exception-handling-c-cpp.md) \(SEH\) 을 사용하십시오.  
  
## 설명  
 `_malloca` 는 요청이 `_ALLOCA_S_THRESHOLD` 가 제공한 특정한 바이트를 넘어서는 경우, 프로그램 스텍 또는 힙에서 `size` 바이트를 할당합니다.   `_malloca` 및 `_alloca` 의 차이는 `_alloca` 는 크기에 따라 항상 스택에 할당한 다는 것입니다.  할당된 메모리를 해제하기 위해 `free` 를 호출하는 허가 또는 요청을 허락하지 않는 `_alloca` 와 달리, `_malloca` 는 메모리 해제를 위해 [\_freea](../../c-runtime-library/reference/freea.md) 를 사용해야 합니다.  디버그 모드에서 `_malloca` 는 항상 힙에서 메모리를 할당 합니다.  
  
 예외 처리기\(EH\) 에서 `_malloca` 를 명시적으로 호출하는 것에는 제한이 있습니다.  x86 프로세서에서 실행되는 EH 루틴은 자신의 메모리의 프레임에서 작동합니다 : 바깥 쪽 함수의 스택 포인터의 현재 위치를 기반으로하지 않는 메모리 공간에서 자신의 작업을 수행 할 수 있습니다.  가장 일반적인 구현은 Windows NT 구조적 예외 처리\(SEH\) 및 C\+\+ catch 절 식에 포함됩니다.  그러므로, EH 루틴 호출에 반환하는 동안 발생한 에러 시나리오 중 하나에서의 명시적인 `_malloca` 호출 :  
  
-   Windows NT SEH 예외 필터 식: `__except` \(`_malloca ()` \)  
  
-   Windows NT SEH 마지막 예외 처리기: `__finally` {`_malloca ()` }  
  
-   C\+\+ EH catch clause expression  
  
 그러나 `_malloca`는 EH 루틴이나 이전에 나열 된 EH 시나리오 중 하나에 의해 호출 된 응용 프로그램 지원 콜백에서 직접적으로 호출 될 수 있습니다.  
  
> [!IMPORTANT]
>  Windows XP 에서, `_malloca` 가 try\/catch 블록에서 호출 된 경우, [\_resetstkoflw](../../c-runtime-library/reference/resetstkoflw.md) 를 호출해야 합니다.  
  
 위의 제한을 사용 하는 경우 외에, [\/clr \(공용 언어 런타임 컴파일\)](../../build/reference/clr-common-language-runtime-compilation.md) 옵션을 사용할 때 `_malloca` 는 `__except` 블록에서 사용될 수 없습니다.  자세한 내용은 [\/clr Restrictions](../../build/reference/clr-restrictions.md) 를 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_malloca`|\<malloc.h\>|  
  
## 예제  
  
```  
// crt_malloca_simple.c  
#include <stdio.h>  
#include <malloc.h>  
  
void Fn()  
{  
   char * buf = (char *)_malloca( 100 );  
   // do something with buf  
   _freea( buf );  
}  
  
int main()  
{  
   Fn();  
}  
```  
  
## 예제  
  
```  
// crt_malloca_exception.c  
// This program demonstrates the use of  
// _malloca and trapping any exceptions  
// that may occur.  
  
#include <windows.h>  
#include <stdio.h>  
#include <malloc.h>  
  
int main()  
{  
    int     size;  
    int     numberRead = 0;  
    int     errcode = 0;  
    void    *p = NULL;  
    void    *pMarker = NULL;  
  
    while (numberRead == 0)  
    {  
        printf_s("Enter the number of bytes to allocate "  
                 "using _malloca: ");  
        numberRead = scanf_s("%d", &size);  
    }  
  
    // Do not use try/catch for _malloca,  
    // use __try/__except, since _malloca throws  
    // Structured Exceptions, not C++ exceptions.  
  
    __try  
    {  
        if (size > 0)  
        {  
            p =  _malloca( size );  
        }  
        else  
        {  
            printf_s("Size must be a positive number.");  
        }  
        _freea( p );  
    }  
  
    // Catch any exceptions that may occur.  
    __except( GetExceptionCode() == STATUS_STACK_OVERFLOW )  
    {  
        printf_s("_malloca failed!\n");  
  
        // If the stack overflows, use this function to restore.  
        errcode = _resetstkoflw();  
        if (errcode)  
        {  
            printf("Could not reset the stack!");  
            _exit(1);  
        }  
    };  
}  
```  
  
## 입력  
  
```  
1000  
```  
  
## 샘플 출력  
  
```  
Enter the number of bytes to allocate using _malloca: 1000  
```  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [메모리 할당](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [\_resetstkoflw](../../c-runtime-library/reference/resetstkoflw.md)