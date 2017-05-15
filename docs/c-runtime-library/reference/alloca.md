---
title: _alloca | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _alloca
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
- _alloca
- alloca
dev_langs:
- C++
helpviewer_keywords:
- memory allocation, stack
- alloca function
- _alloca function
ms.assetid: 74488eb1-b71f-4515-88e1-cdd03b6f8225
caps.latest.revision: 23
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 5875a26dc5758674665fba2fde5b51c2ff53420e
ms.contentlocale: ko-kr
ms.lasthandoff: 03/30/2017

---
# <a name="alloca"></a>_alloca
스택에 메모리를 할당합니다. 더 안전한 버전을 사용할 수 있습니다; 때문에이 함수는 사용 되지 않습니다. 참조 [_malloca](../../c-runtime-library/reference/malloca.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void *_alloca(   
   size_t size   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 [in] `size`  
 스택에서 할당할 바이트입니다.  
  
## <a name="return-value"></a>반환 값  
 `_alloca` 루틴은 할당된 공간에 대한 `void` 포인터를 반환하며, 이 공간은 모든 형식의 개체 저장소에 적절하게 맞춰지도록 보장됩니다. `size`가 0이면 `_alloca`는 길이가 0인 항목을 할당하고 해당 항목에 대한 유효한 포인터를 반환합니다.  
  
 공간을 할당할 수 없는 경우 스택 오버플로 예외가 생성됩니다. 스택 오버플로 예외는 C++ 예외가 아니며 구조적 예외입니다. C++ 예외 처리를 사용하는 대신 [SEH(구조적 예외 처리)](../../cpp/structured-exception-handling-c-cpp.md)를 사용해야 합니다.  
  
## <a name="remarks"></a>설명  
 `_alloca`할당 `size` 프로그램 스택에서 바이트입니다. 할당 된 공간 (때가 아니라 단지 할당 범위 밖으로 나갈)는 호출 함수가 종료 될 때에 자동으로 해제 됩니다. 따라서에서 반환 된 포인터 값을 전달 하지 마십시오 `_alloca` 인수로 [무료](../../c-runtime-library/reference/free.md)합니다.  
  
 EH(예외 처리기)에서 `_alloca`를 명시적으로 호출하는 데는 제한이 있습니다. x86급 프로세서에서 실행되는 EH 루틴은 고유한 메모리 프레임에서 작동합니다. 즉, 바깥쪽 함수 스택 포인터의 현재 위치를 기반으로 하지 않는 메모리 공간에서 해당 작업을 수행합니다. 가장 일반적인 구현에는 Windows NT SEH(구조적 예외 처리) 및 C++ catch 절 식이 포함됩니다. 따라서 다음 시나리오 중 하나에서 `_alloca`를 명시적으로 호출하면 호출 EH 루틴으로 돌아가는 동안 프로그램 오류가 발생합니다.  
  
-   Windows NT SEH 예외 필터 식: `__except` (`_alloca ()` )  
  
-   Windows NT SEH 최종 예외 처리기: `__finally` {`_alloca ()` }  
  
-   C++ EH catch 절 식  
  
 그러나 `_alloca`는 EH 루틴 내에서 또는 위에 나열된 EH 시나리오 중 하나에서 호출되는 응용 프로그램 제공 콜백에서 직접 호출할 수 있습니다.  
  
> [!IMPORTANT]
>  Windows XP의 경우 try/catch 블록 내에서 `_alloca`를 호출하면 catch 블록에서 [_resetstkoflw](../../c-runtime-library/reference/resetstkoflw.md)를 호출해야 합니다.  
  
 위의 제한을 사용 하는 경우 외에도[/clr (공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md) 옵션을 `_alloca` 에 사용할 수 없는 `__except` 블록. 자세한 내용은 [/clr Restrictions](../../build/reference/clr-restrictions.md)을 참조하십시오.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_alloca`|\<malloc.h>|  
  
## <a name="example"></a>예제  
  
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
  
```Output  
Allocated 1000 bytes of stack at 0x0012FB50  
```  
  
## <a name="see-also"></a>참고 항목  
 [메모리 할당](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [_resetstkoflw](../../c-runtime-library/reference/resetstkoflw.md)   
 [_malloca](../../c-runtime-library/reference/malloca.md)
