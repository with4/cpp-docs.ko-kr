---
title: "_resetstkoflw | Microsoft Docs"
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
  - "_resetstkoflw"
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
  - "resetstkoflw"
  - "_resetstkoflw"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_resetstkoflw 함수"
  - "resetstkoflw 함수"
  - "스택 오버플로"
  - "스택, 복구"
ms.assetid: 319529cd-4306-4d22-810b-2063f3ad9e14
caps.latest.revision: 20
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _resetstkoflw
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

스택 오버플로를 복구합니다.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
  
int _resetstkoflw ( void );  
  
```  
  
## 반환 값  
 함수가 성공 하면 0이고 실패 하면 0입니다.  
  
## 설명  
 `_resetstkoflw` 함수는 스택 오버플로 상태를 복구하여 프로그램이 치명적 예외 오류와 함께 실패하는 대신 계속 실행되도록 합니다.  `_resetstkoflw` 함수를 호출하지 않으면 앞의 예외 다음에는 가드 페이지가 없게 됩니다.  다음에 스택 오버플로가 발생하면 예외가 전혀 발생하지 않고 프로세스가 경고 없이 종료됩니다.  
  
 스레드 응용 프로그램에서 발생 하는 경우는 **EXCEPTION\_STACK\_OVERFLOW** 예외 스레드는 스택이 손상된 상태로 남겨집니다.  이와 반대로 다른 예외와 같은 **EXCEPTION\_ACCESS\_VIOLATION** 또는 **EXCEPTION\_INT\_DIVIDE\_BY\_ZERO**스택 손상 되지 않았는지 대조합니다.  프로그램이 처음 로드 될 때 스택은 임의로 작은 값으로 설정 됩니다.  스택 다음 스레드가 요구를 충족 시키기에 필요에 따라 증가 합니다.  현재 스택의 끝 PAGE\_GUARD 접근할 수 있는 페이지를 배치하여 구현 됩니다.  자세한 내용은 [하위 쿼리 만들기](http://msdn.microsoft.com/library/windows/desktop/aa366549)를 참조하십시오.  
  
 코드는 이 페이지의 주소를 가리키도록 스택 포인터를 야기시킬 경우 , 예외가 발생하고 시스템에서 다음 세 가지를 따릅니다. :  
  
-   스레드 읽기 및 메모리에 데이터를 쓸 수 있도록 가드 페이지의 PAGE\_GUARD 보호를 제거 합니다.  
  
-   새 가드 할당 즉 있는 한 페이지 아래쪽에 마지막 페이지입니다.  
  
-   예외를 발생 시킨 명령을 다시 실행 합니다.  
  
 이렇게 시스템 크기를 늘릴 수 있는 스레드에 대한 스택 자동으로 증가시킵니다.  각 스레드는 프로세스의 최대 스택 크기가 되었습니다.  스택 크기는 [\/STACK\(스택 할당\)](../../build/reference/stack-stack-allocations.md)에 의한 컴파일 시간을 설정합니다. 또는 [STACKSIZE](../../build/reference/stacksize.md) 프로젝트에 대한.def 파일 명세서를 설정합니다.  
  
 이 최대 스택 크기를 초과 하는 경우 시스템은 다음 세 가지를 따릅니다. :  
  
-   가드 페이지 앞에서 설명한 대로 PAGE\_GUARD 보호를 제거 합니다.  
  
-   마지막 아래에 새 가드 페이지를 할당 하려고 시도 합니다.  그러나 최대 스택 크기를 초과 했기 때문에 실패 합니다.  
  
-   스레드는 예외 블록에서 처리할 수 있도록 예외를 발생 시킵니다.  
  
 ,이 시점에서 스택은 더 이상 가드 페이지가 아닙니다.  다음시간은 프로그램이 끝까지 스택을 시킵니다. 가드페이지가 있는 곳에서 프로그램은 스택의 끝에서부터 쓰여지며 접근 위반을 야기시킵니다.  
  
 `_resetstkoflw` 는 스택 오버플로우 예외를 복구할 때마다, 가드 페이지를 복원하기 위하여 호출합니다.  본문 내에서 이 함수를 호출할 수 있는 `__except` 블록이거나 **\_\_except** 블럭 밖입니다.  그러나 사용할 때 몇 가지 제한 사항이 있습니다.  `_resetstkoflw` 호출하면 안 됩니다.:  
  
-   필터 식입니다.  
  
-   filter 함수\[F\#\]  
  
-   필터 함수에서 호출 하는 함수입니다.  
  
-   하나의 **catch** 블록  
  
-   `__finally` 블록.  
  
 이러한 점에서, 스택은 충분하게 아직 해제되지 않습니다.  
  
 스택 오버플로우 예외는 c \+ \+ 예외가 아닌, 구조화된 예외로 발생됩니다, 따라서, 스택 오버플로우 예외는 catch되지 않기 때문에 `_resetstkoflw` 는 일반적인 **catch** 블럭에서는 유용하지 않습니다.  그러나, [\_set\_se\_translator](../../c-runtime-library/reference/set-se-translator.md) 가 스택 오버플로 예외 \(예: 두 번째 예제에서는\) c \+ \+ 예외를 throw 하는 구조화된 예외 변환기를 구현하는데 이용될 경우, c \+ \+ catch 블록에서 처리할 수 있는 c \+ \+ 예외가 발생합니다.  
  
 구조화된 예외 변환기 함수로부터 throw 된 예외로부터 도달하는 c \+ \+ catch 블록에서 **\_resetstkoflw** 를 호출하는 것은 안전하지 않습니다.  이 경우, catch 블록 외부도 심지어 소멸자가 catch 블럭 전에 모든 소멸자 개체들에 대해 호출될 때까지 스택 공간이 해제 되지 않고 스택 포인터는 다시 설정되지 않습니다.  스택 공간이 확보되고 스택 포인터를 다시 설정할 때까지 이 함수를 호출합니다.  따라서 catch 블록을 종료 한 후에 호출해야 합니다.  가급적 작은 스택 공간은 catch 블럭에서 이용되어야만 합니다. catch 블럭에서 오버플로우는 동일한 catch 블럭에 의해 스스로 다뤄지는 예외를 촉발시키는데, 전 스택 오버플로우로부터 복구되길 스스로 시도했던 catch블럭에서 발생하는 오버플로우는 복구될 수 없고 프로그램이 반응을 멈추는 것을 야기하기 때문입니다.  
  
 **\_\_except** 블록과 같이, 올바른 위치로 설령 사용되더라도, **\_resetstkoflw** 이 실패인 상황입니다.  심지어 스택 해제 후에도, 스택의 마지막 페이지에서 쓰이는 것 없이 **\_resetstkoflw** 가 실행되기 위해 남겨진 스택 공간은 충분하지 않을 경우, **\_resetstkoflw** 는 가드 페이지로서 스택의 마지막 페이지를 다시 설정하는 데 실패합니다. 그 결과 0을 반환하고, 실패를 암시합니다.  그러므로 이 함수의 안전한 사용량은 스택을 사용하는데 안전함을 가정하는 대신 반환 값을 확인하는 것을 포함해야 합니다.  
  
 구조화된 예외 처리는 `STATUS_STACK_OVERFLOW` 응용 프로그램을 catch할 것입니다. `/clr` 또는 `/clr:pure` 을 컴파일할 때입니다. \(참조 [\/clr\(공용 언어 런타임 컴파일\)](../../build/reference/clr-common-language-runtime-compilation.md)\).  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_resetstkoflw`|\<malloc.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
 **라이브러리:** 의 모든 버전은 [CRT 라이브러리 기능](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 예제  
 다음 코드 예제에서는 `_resetstkoflw` 함수를 사용하는 방법을 보여 줍니다.  
  
```  
// crt_resetstkoflw.c  
// Launch program with and without arguments to observe  
// the difference made by calling _resetstkoflw.  
  
#include <malloc.h>  
#include <stdio.h>  
#include <windows.h>  
  
void recursive(int recurse)  
{  
   _alloca(2000);  
   if (recurse)  
      recursive(recurse);  
}  
  
// Filter for the stack overflow exception.  
// This function traps the stack overflow exception, but passes  
// all other exceptions through.   
int stack_overflow_exception_filter(int exception_code)  
{  
   if (exception_code == EXCEPTION_STACK_OVERFLOW)  
   {  
       // Do not call _resetstkoflw here, because  
       // at this point, the stack is not yet unwound.  
       // Instead, signal that the handler (the __except block)  
       // is to be executed.  
       return EXCEPTION_EXECUTE_HANDLER;  
   }  
   else  
       return EXCEPTION_CONTINUE_SEARCH;  
}  
  
int main(int ac)  
{  
   int i = 0;  
   int recurse = 1, result = 0;  
  
   for (i = 0 ; i < 10 ; i++)  
   {  
      printf("loop #%d\n", i + 1);  
      __try  
      {  
         recursive(recurse);  
  
      }  
  
      __except(stack_overflow_exception_filter(GetExceptionCode()))  
      {  
         // Here, it is safe to reset the stack.  
  
         if (ac >= 2)  
         {  
            puts("resetting stack overflow");  
            result = _resetstkoflw();  
         }  
      }  
  
      // Terminate if _resetstkoflw failed (returned 0)  
      if (!result)  
         return 3;  
   }  
  
   return 0;  
}  
```  
  
## 샘플 출력  
 프로그램 인수 없이.  
  
```  
loop #1  
```  
  
 프로그램이 반복을 실행 하지 않고 응답 하지 않습니다.  
  
 프로그램 인수 없이.  
  
```  
loop #1  
resetting stack overflow  
loop #2  
resetting stack overflow  
loop #3  
resetting stack overflow  
loop #4  
resetting stack overflow  
loop #5  
resetting stack overflow  
loop #6  
resetting stack overflow  
loop #7  
resetting stack overflow  
loop #8  
resetting stack overflow  
loop #9  
resetting stack overflow  
loop #10  
resetting stack overflow  
```  
  
### 설명  
 다음 예제에서는 구조화된 예외가 c \+ \+ 예외로 변환되는 프로그램에서 권장되는 사용인 `_resetstkoflw` 을 보여줍니다.  
  
### 코드  
  
```  
// crt_resetstkoflw2.cpp  
// compile with: /EHa  
// _set_se_translator requires the use of /EHa  
#include <malloc.h>  
#include <stdio.h>  
#include <windows.h>  
#include <eh.h>  
  
class Exception { };  
  
class StackOverflowException : Exception { };  
  
// Because the overflow is deliberate, disable the warning that  
// this function will cause a stack overflow.  
#pragma warning (disable: 4717)  
void CauseStackOverflow (int i)  
{  
        // Overflow the stack by allocating a large stack-based array  
        // in a recursive function.  
        int a[10000];  
        printf("%d ", i);  
        CauseStackOverflow (i + 1);  
}  
  
void __cdecl SEHTranslator (unsigned int code, _EXCEPTION_POINTERS*)  
{  
   // For stack overflow exceptions, throw our own C++   
   // exception object.  
   // For all other exceptions, throw a generic exception object.  
   // Use minimal stack space in this function.  
   // Do not call _resetstkoflw in this function.  
  
   if (code == EXCEPTION_STACK_OVERFLOW)  
      throw StackOverflowException ( );  
   else  
      throw Exception( );  
}  
  
int main ( )  
{  
        bool stack_reset = false;  
        bool result = false;  
  
        // Set up a function to handle all structured exceptions,  
        // including stack overflow exceptions.  
        _set_se_translator (SEHTranslator);  
  
        try  
        {  
            CauseStackOverflow (0);  
        }  
        catch (StackOverflowException except)  
        {  
                // Use minimal stack space here.  
                // Do not call _resetstkoflw here.  
                printf("\nStack overflow!\n");  
                stack_reset = true;  
        }  
        catch (Exception except)  
        {  
                // Do not call _resetstkoflw here.  
                printf("\nUnknown Exception!\n");  
        }  
        if (stack_reset)  
        {  
          result = _resetstkoflw();  
          // If stack reset failed, terminate the application.  
          if (result == 0)  
             exit(1);  
        }  
  
        void* pv = _alloca(100000);  
        printf("Recovered from stack overflow and allocated 100,000 bytes"  
               " using _alloca.");  
  
   return 0;  
}  
```  
  
## 샘플 출력  
  
```  
0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24  
Stack overflow!  
Recovered from stack overflow and allocated 100,000 bytes using _alloca.  
```  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [\_alloca](../../c-runtime-library/reference/alloca.md)