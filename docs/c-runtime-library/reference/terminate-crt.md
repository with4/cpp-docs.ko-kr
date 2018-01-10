---
title: terminate(CRT) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: terminate
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords: terminate
dev_langs: C++
helpviewer_keywords:
- terminate function
- exception handling, termination
ms.assetid: 90e67402-08e9-4b2a-962c-66a8afd3ccb4
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b04cd56f2239bcee291a0de37f23f7eb2e699f1a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="terminate-crt"></a>terminate(CRT)
`abort`를 사용하여 `set_terminate` 또는 사용자가 지정하는 함수를 호출합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void terminate( void );  
```  
  
## <a name="remarks"></a>설명  
 `terminate` 함수는 C++ 예외 처리와 함께 사용되며 다음과 같은 경우에 호출됩니다.  
  
-   throw된 C++ 예외에 대해 일치하는 catch 처리기를 찾을 수 없는 경우  
  
-   스택 해제 중에 소멸자 함수가 예외를 throw한 경우  
  
-   스택이 예외를 throw한 후에 손상된 경우  
  
 `terminate`는 기본적으로 `abort`를 호출합니다. 종료 함수를 직접 작성하고 함수 이름을 인수로 사용해 `set_terminate`를 호출하면 이 기본값을 변경할 수 있습니다. `terminate`는 `set_terminate`에 대한 인수로 지정된 마지막 함수를 호출합니다. 자세한 내용은 [처리되지 않은 C++ 예외](../../cpp/unhandled-cpp-exceptions.md)를 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`terminate`|\<eh.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## <a name="example"></a>예  
  
```  
// crt_terminate.cpp  
// compile with: /EHsc  
#include <eh.h>  
#include <process.h>  
#include <iostream>  
using namespace std;  
  
void term_func();  
  
int main()  
{  
    int i = 10, j = 0, result;  
    set_terminate( term_func );  
    try  
    {  
        if( j == 0 )  
            throw "Divide by zero!";  
        else  
            result = i/j;  
    }  
    catch( int )  
    {  
        cout << "Caught some integer exception.\n";  
    }  
    cout << "This should never print.\n";  
}  
  
void term_func()  
{  
    cout << "term_func() was called by terminate().\n";  
  
    // ... cleanup tasks performed here  
  
    // If this function does not exit, abort is called.  
  
    exit(-1);  
}  
```  
  
```Output  
term_func() was called by terminate().  
```  
  
## <a name="see-also"></a>참고 항목  
 [예외 처리 루틴](../../c-runtime-library/exception-handling-routines.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [_set_se_translator](../../c-runtime-library/reference/set-se-translator.md)   
 [set_terminate](../../c-runtime-library/reference/set-terminate-crt.md)   
 [set_unexpected](../../c-runtime-library/reference/set-unexpected-crt.md)   
 [unexpected](../../c-runtime-library/reference/unexpected-crt.md)