---
title: "terminate(CRT) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "terminate"
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
  - "terminate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "예외 처리, 종료"
  - "terminate 함수"
ms.assetid: 90e67402-08e9-4b2a-962c-66a8afd3ccb4
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# terminate(CRT)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`abort` 또는 `set_terminate`를 사용하여 사용자가 지정한 함수를 호출하세요.  
  
## 구문  
  
```  
void terminate( void );  
```  
  
## 설명  
 `terminate` 함수는 C\+\+ 예외 처리와 함께 사용되며 다음과 같은 경우에 호출됩니다.  
  
-   발생한 C\+\+ 예외에 해당하는 예외 처리기를 찾을 수 없습니다.  
  
-   스택이 해제되는 동안 소멸자 함수에서 예외가 발생합니다.  
  
-   스택은 예외가 발생한 후 손상되었습니다.  
  
 `terminate`는 `abort`를 기본적으로 호출합니다.  사용자는 자신만의 종료 함수를 작성하고 `set_terminate`를 사용자의 함수 이름과 매개변수로 호출함으로써 이 기본값을 변경할 수 있습니다.  `terminate` 루틴은 `set_terminate`에 대한 인수로 주어진 마지막 함수를 항상 호출합니다.  자세한 내용은 [처리되지 않은 C\+\+ 예외](../../cpp/unhandled-cpp-exceptions.md)를 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`terminate`|\<eh.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
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
  
  **terminate\(\)에서 term\_func\(\)가 호출되었습니다.**   
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [예외 처리 루틴](../../c-runtime-library/exception-handling-routines.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [\_set\_se\_translator](../../c-runtime-library/reference/set-se-translator.md)   
 [set\_terminate](../../c-runtime-library/reference/set-terminate-crt.md)   
 [set\_unexpected](../../c-runtime-library/reference/set-unexpected-crt.md)   
 [unexpected](../../c-runtime-library/reference/unexpected-crt.md)