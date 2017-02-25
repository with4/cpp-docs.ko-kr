---
title: "_set_se_translator | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_set_se_translator"
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
  - "_set_se_translator"
  - "set_se_translator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_set_se_translator 함수"
  - "예외 처리, 변경"
  - "set_se_translator 함수"
ms.assetid: 280842bc-d72a-468b-a565-2d3db893ae0f
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# _set_se_translator
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

C\+\+ 예외 형식 같은 Win32 예외 처리 \(C 구조적 예외\)  
  
## 구문  
  
```  
_se_translator_function _set_se_translator(  
   _se_translator_function seTransFunction  
);  
```  
  
#### 매개 변수  
 `seTransFunction`  
 당신이 쓰는 C 구조적 예외 번환기 함수에 대한 포인터입니다.  
  
## 반환 값  
 `_set_se_translator` 가 등록한 이전의 변환 함수를 가르키는 포인터를 반환합니다. 그러므로 이전 함수는 이후에 복원될 수 있습니다.  이전 함수가 설정되어 있지 않은 경우, 반환 값은 기본 기능을 복원하는데 사용 될 수 있습니다 이 값은 NULL 일 수 있습니다.  
  
## 설명  
 `_set_se_translator` 함수는 C\+\+ 형식인 예외로서 Win32 예외를 처리하는 방법을 제공합니다\(C 구조적 예외\)  각 C 예외가 C\+\+`catch` 처리기로 처리 될 수 있도록, C 예외에 대한 특정 클래스 형식의 특성에 사용되거나 파생될 C 예외 래퍼 클래스를 처음 정의합니다.  이 클래스를 사용하려면 C 예외가 발생할 때 마다 내부 예외 처리 메커니즘을 통해 호출되는 사용자 지정 C 예외 변환 함수를 설치합니다.  번역기 함수 내에서, C\+\+ `catch` 처리기에 일치하여 catch할 수 있는 모든 형식의 예외를 throw 할 수 있습니다.  
  
 `_set_se_translator` 를 사용 할 때 [\/EHa](../../build/reference/eh-exception-handling-model.md) 를 사용해야 합니다.  
  
 사용자 지정 변환 함수를 지정하려면, 인수로 변환 함수의 이름을 사용하여 `_set_se_translator`  를 호출하십시오.  사용자가 작성한 변환 함수는 `try`  블럭을 가진 스택에서 각 함수 호출에 대해 한번 호출 됩니다.  기본 변환 함수는 없습니다.  
  
 변환 함수는 C\+\+ 형식의 예외가 발생보다 더 많을 수도 있습니다.  throw 이외에 아무것도 않는 경우, 변환 함수가 호출되는 횟수는 플랫폼에 의존하기 때문에 프로그램이 작동하지 않을 수 있습니다 \(예를 들어, 로그 파일에 쓰기\)  
  
 다중 스레드 환경에서 변환 기능은 각 스레드에 대해 개별적으로 유지됩니다  각 새 스레드에 변환 기능을 설치 해야 합니다.  따라서 각 스레드는 변환 처리를 가집니다.  `_set_se_translator`  는 다른 DLL이 다른 변환 기능을 설치 할 수 있는 하나의 스레드에 지정합니다.  
  
 사용자가 작성하는 `seTransFunction` 함수는네이티브 컴파일 함수여야 합니다\( \/clr을 사용하여 컴파일 되지 않은\)  인수로서 부호없는 정수와 Win32 `_EXCEPTION_POINTERS` 구초제에 대한 포인터를 사용합니다.  인수는 Wind 32 API `GetExceptionCode` and `GetExceptionInformation` 함수에 대한 호출의 결과 값을 반환합니다.  
  
```  
typedef void (*_se_translator_function)(unsigned int, struct _EXCEPTION_POINTERS* );  
```  
  
 `_set_se_translator` 에 대해, 동적으로 CRT에 연결하는 의미가 있으며 그 과정에서 다른 DLL이 `_set_se_translator` 를 호출하고 핸들러를 대체 할 수 있습니다.  
  
 관리 코드\(\/clr 을 사용하여 컴파일한 코드\) 또는 혼합된 네이티브와 관리 코드에서 `_set_se_translator` 를 사용하는 경우, 변환은 네이티브 코드에서만 생성된 예외에 영향을 미칩니다.  관리 코드에서 생성 되는 관리 예외는 \(`System::Exception`\) 변환 함수를 통해 라우팅되지 않습니다.  Win32 함수 `RaiseException`를 사용하여 관리 코드에서 발생하는 예외 또는 0으로 나누기와 같은 시스템 예외로 인한 예외는 변환기를 통해 라우팅됩니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_set_se_translator`|\<eh.h\>|  
  
 [\/clr:pure](../../build/reference/clr-common-language-runtime-compilation.md) 컴파일 옵션을 사용하여 컴파일한 코드에서 기능으로 `_set_se_translator` 가 제공하는 것은 사용할 수 없습니다.  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_settrans.cpp  
// compile with: /EHa  
#include <stdio.h>  
#include <windows.h>  
#include <eh.h>  
  
void SEFunc();  
void trans_func( unsigned int, EXCEPTION_POINTERS* );  
  
class SE_Exception  
{  
private:  
    unsigned int nSE;  
public:  
    SE_Exception() {}  
    SE_Exception( unsigned int n ) : nSE( n ) {}  
    ~SE_Exception() {}  
    unsigned int getSeNumber() { return nSE; }  
};  
int main( void )  
{  
    try  
    {  
        _set_se_translator( trans_func );  
        SEFunc();  
    }  
    catch( SE_Exception e )  
    {  
        printf( "Caught a __try exception with SE_Exception.\n" );  
    }  
}  
void SEFunc()  
{  
    __try  
    {  
        int x, y=0;  
        x = 5 / y;  
    }  
    __finally  
    {  
        printf( "In finally\n" );  
    }  
}  
void trans_func( unsigned int u, EXCEPTION_POINTERS* pExp )  
{  
    printf( "In trans_func.\n" );  
    throw SE_Exception();  
}  
```  
  
  **In trans\_func.**  
**In finally**  
**Caught a \_\_try exception with SE\_Exception.**   
## 예제  
 비록 `_set_se_translator` 가 제공하는 기능은 관리 코드에서 사용할 수 없지만, `/clr` 에서 컴파일 된 네이티브 코드라도 `#pragma unmanaged` 를 사용하여 표시되는 네이티브 코드인 한 네이티브 코드에서 이 매핑을 사용하는 것은 가능합니다.   매핑 된 관리 코드에서 구조적인 예외가 throw 된 경우, 예외를 생성하고 처리하는 코드는 `pragma` 에 표시 됩니다.  다음 코드에서는 가능한 사용법을 보여줍니다  자세한 내용은 [Pragma 지시문 및 \_\_Pragma 키워드](../../preprocessor/pragma-directives-and-the-pragma-keyword.md)을 참조하십시오.  
  
```  
// crt_set_se_translator_clr.cpp  
// compile with: /clr  
#include <windows.h>  
#include <eh.h>  
#include <assert.h>  
#include <stdio.h>  
  
int thrower_func(int i) {  
   int j = i/0;  
  return 0;  
}  
  
class CMyException{  
};  
  
#pragma unmanaged  
void my_trans_func(unsigned int u, PEXCEPTION_POINTERS pExp )  
{  
printf("Translating the structured exception to a C++"  
             " exception.\n");  
throw CMyException();  
}  
  
void DoTest()  
{  
    try  
    {  
      thrower_func(10);  
    }   
  
    catch(CMyException e)  
    {  
printf("Caught CMyException.\n");  
    }  
    catch(...)  
    {  
      printf("Caught unexpected SEH exception.\n");  
    }  
}  
#pragma managed  
  
int main(int argc, char** argv) {  
    _set_se_translator(my_trans_func);  
    DoTest();  
    return 0;  
}  
```  
  
  **구조적인 예외를 C\+\+ 예외로 변환합니다.**  
**Caught CMyException.**   
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [예외 처리 루틴](../../c-runtime-library/exception-handling-routines.md)   
 [set\_terminate](../../c-runtime-library/reference/set-terminate-crt.md)   
 [set\_unexpected](../../c-runtime-library/reference/set-unexpected-crt.md)   
 [terminate](../../c-runtime-library/reference/terminate-crt.md)   
 [unexpected](../../c-runtime-library/reference/unexpected-crt.md)