---
title: "_malloca | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _malloca
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- malloca
- _malloca
dev_langs:
- C++
helpviewer_keywords:
- memory allocation, stack
- malloca function
- _malloca function
ms.assetid: 293992df-cfca-4bc9-b313-0a733a6bb936
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d61874320712e6cef7f783bb1c4fb03f53ac40e9
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="malloca"></a>_malloca
스택에 메모리를 할당합니다. [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 있는 [_alloca](../../c-runtime-library/reference/alloca.md) 버전입니다.  
  
## <a name="syntax"></a>구문  
  
```  
void *_malloca(   
   size_t size   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `size`  
 스택에서 할당할 바이트입니다.  
  
## <a name="return-value"></a>반환 값  
 `_malloca` 루틴은 할당된 공간에 대한 `void` 포인터를 반환하며, 이 공간은 모든 형식의 개체 저장소에 적절하게 맞춰지도록 보장됩니다. `size`가 0이면 `_malloca`는 길이가 0인 항목을 할당하고 해당 항목에 대한 유효한 포인터를 반환합니다.  
  
 공간을 할당할 수 없는 경우 스택 오버플로 예외가 생성됩니다. 스택 오버플로 예외는 C++ 예외가 아니며 구조적 예외입니다. C++ 예외 처리를 사용하는 대신 [SEH(구조적 예외 처리)](../../cpp/structured-exception-handling-c-cpp.md)를 사용해야 합니다.  
  
## <a name="remarks"></a>설명  
 `_malloca`는 요청이 `_ALLOCA_S_THRESHOLD`에서 제공하는 특정 크기(바이트)를 초과하는 경우 프로그램 스택이나 힙에서 `size` 바이트를 할당합니다. `_malloca`와 `_alloca`의 차이점은 `_alloca`는 크기에 관계없이 항상 스택에서 할당한다는 점입니다. 메모리를 확보하여 할당하기 위해 `free` 호출이 필요하거나 이 호출을 허용할 필요가 없는 `_alloca`와 달리 `_malloca`는 메모리를 확보하려면 [_freea](../../c-runtime-library/reference/freea.md)를 사용해야 합니다. 디버그 모드에서 `_malloca`는 항상 힙에서 메모리를 할당합니다.  
  
 EH(예외 처리기)에서 `_malloca`를 명시적으로 호출하는 데는 제한이 있습니다. x86급 프로세서에서 실행되는 EH 루틴은 고유한 메모리 프레임에서 작동합니다. 즉, 바깥쪽 함수 스택 포인터의 현재 위치를 기반으로 하지 않는 메모리 공간에서 해당 작업을 수행합니다. 가장 일반적인 구현에는 Windows NT SEH(구조적 예외 처리) 및 C++ catch 절 식이 포함됩니다. 따라서 다음 시나리오 중 하나에서 `_malloca`를 명시적으로 호출하면 호출 EH 루틴으로 돌아가는 동안 프로그램 오류가 발생합니다.  
  
-   Windows NT SEH 예외 필터 식: `__except` (`_malloca ()` )  
  
-   Windows NT SEH 최종 예외 처리기: `__finally` {`_malloca ()` }  
  
-   C++ EH catch 절 식  
  
 그러나 `_malloca`는 EH 루틴 내에서 또는 위에 나열된 EH 시나리오 중 하나에서 호출되는 응용 프로그램 제공 콜백에서 직접 호출할 수 있습니다.  
  
> [!IMPORTANT]
>  Windows XP의 경우 try/catch 블록 내에서 `_malloca`를 호출하면 catch 블록에서 [_resetstkoflw](../../c-runtime-library/reference/resetstkoflw.md)를 호출해야 합니다.  
  
 위의 제한 외에도 [/clr(공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md) 옵션을 사용하는 경우 `_malloca`는 `__except` 블록에서 사용할 수 없습니다. 자세한 내용은 [/clr 제한](../../build/reference/clr-restrictions.md)을 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`_malloca`|\<malloc.h>|  
  
## <a name="example"></a>예  
  
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
  
## <a name="example"></a>예  
  
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
  
## <a name="input"></a>입력  
  
```  
1000  
```  
  
## <a name="sample-output"></a>샘플 출력  
  
```  
Enter the number of bytes to allocate using _malloca: 1000  
```  
  
## <a name="see-also"></a>참고 항목  
 [메모리 할당](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [_resetstkoflw](../../c-runtime-library/reference/resetstkoflw.md)