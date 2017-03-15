---
title: _set_se_translator | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _set_se_translator
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
- _set_se_translator
- set_se_translator
dev_langs:
- C++
helpviewer_keywords:
- set_se_translator function
- exception handling, changing
- _set_se_translator function
ms.assetid: 280842bc-d72a-468b-a565-2d3db893ae0f
caps.latest.revision: 21
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
translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: d8d43b39c9f71807d68f20cb4873abf96d3f91e8
ms.lasthandoff: 02/24/2017

---
# <a name="setsetranslator"></a>_set_se_translator
Win32 예외(C 구조적 예외)를 C++ 형식 예외로 처리합니다.  
  
## <a name="syntax"></a>구문  
  
```  
_se_translator_function _set_se_translator(  
   _se_translator_function seTransFunction  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `seTransFunction`  
 작성하는 C 구조적 예외 변환기 함수에 대한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 이전 함수를 나중에 복원할 수 있도록 `_set_se_translator`에서 등록한 이전 변환기 함수에 대한 포인터를 반환합니다. 이전 함수가 설정되지 않은 경우 반환 값을 사용하여 기본 동작을 복원할 수 있습니다. 이 값은 NULL일 수 있습니다.  
  
## <a name="remarks"></a>설명  
 `_set_se_translator` 함수는 Win32 예외(C 구조적 예외)를 C++ 형식 예외로 처리하는 방법을 제공합니다. 각 C 예외가 C++ `catch` 처리기에 의해 처리되도록 허용하려면 먼저 특정 클래스 형식의 특성을 C 예외로 지정하도록 사용 또는 파생될 수 있는 C 예외 래퍼 클래스를 정의합니다. 이 클래스를 사용하려면 C 예외가 발생할 때마다 내부 예외 처리 메커니즘을 통해 호출되는 사용자 지정 C 예외 변환기 함수를 설치합니다. 변환기 함수 내에서 일치하는 C++ `catch` 처리기에 의해 catch될 수 있는 모든 형식의 예외를 throw할 수 있습니다.  
  
 `_set_se_translator`를 사용할 때 [/EHa](../../build/reference/eh-exception-handling-model.md)를 사용해야 합니다.  
  
 사용자 지정 변환 함수를 지정하려면 변환 함수의 이름을 인수로 사용하여 `_set_se_translator`를 호출합니다. 사용자가 작성한 변환기 함수는 `try` 블록이 있는 스택의 각 함수 호출에 대해 한 번씩 호출됩니다. 기본 변환기 함수가 없습니다.  
  
 변환기 함수는 C++ 형식의 예외만 발생시켜야 합니다. throw 이외에도 어떤 작업을 수행하는 경우(예: 로그 파일에 쓰기) 변환기 함수가 호출되는 횟수가 플랫폼에 따라 다르므로 프로그램이 예상대로 작동하지 않을 수 있습니다.  
  
 다중 스레드 환경에서 변환기 함수는 각 스레드에 대해 개별적으로 유지 관리됩니다. 각 새 스레드는 자체 변환기 함수를 설치해야 합니다. 따라서 각 스레드는 자체 변환 처리를 담당합니다. `_set_se_translator`는 한 스레드에 해당됩니다. 다른 DLL은 다른 변환 함수를 설치할 수 있습니다.  
  
 사용자가 작성하는 `seTransFunction` 함수는 네이티브 컴파일 함수여야 합니다(/clr을 사용하여 컴파일되지 않음). 이 함수는 부호 없는 정수 및 Win32 `_EXCEPTION_POINTERS` 구조체에 대한 포인터를 인수로 사용해야 합니다. 인수는 각각 Win32 API `GetExceptionCode` 및 `GetExceptionInformation` 함수에 대한 호출의 반환 값입니다.  
  
```  
typedef void (*_se_translator_function)(unsigned int, struct _EXCEPTION_POINTERS* );  
```  
  
 `_set_se_translator`의 경우 동적으로 CRT에 연결할 때 의미하는 사항이 있습니다. 즉, 프로세스의 다른 DLL이 `_set_se_translator`를 호출하고 처리기를 자체 처리기로 대체할 수 있습니다.  
  
 관리 코드(/clr을 사용하여 컴파일된 코드) 또는 혼합된 네이티브 및 관리 코드에서 `_set_se_translator`를 사용할 때 변환기가 네이티브 코드로 생성된 예외에만 영향을 줍니다. 관리 코드에서 생성된 관리 예외(예: `System::Exception`을 발생시키는 경우)는 변환기 함수를 통해 라우팅되지 않습니다. Win32 함수 `RaiseException`을 사용하여 관리 코드에서 발생하는 예외 또는&0;으로 나누기 예외와 같은 시스템 예외에 의해 발생하는 예외가 변환기를 통해 라우팅됩니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_set_se_translator`|\<eh.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
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
  
```Output  
In trans_func.  
In finally  
Caught a __try exception with SE_Exception.  
```  
  
## <a name="example"></a>예제  
 `_set_se_translator`에서 제공되는 기능을 관리 코드에서 사용할 수 없지만 `/clr`를 사용하여 네이티브 코드를 표시하는 동안 해당 네이티브 코드가 `#pragma unmanaged` 스위치 아래에서 컴파일되는 경우에도 이 매핑을 네이티브 코드에서 사용할 수 있습니다. 매핑될 관리 코드에서 구조적 예외가 throw되는 경우 예외를 생성하고 처리하는 코드는 `pragma`로 표시되어야 합니다. 다음 코드에서는 가능한 사용법을 보여 줍니다. 자세한 내용은 [Pragma 지시문 및 __Pragma 키워드](../../preprocessor/pragma-directives-and-the-pragma-keyword.md)를 참조하세요.  
  
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
  
```Output  
Translating the structured exception to a C++ exception.  
Caught CMyException.  
```  
  
## <a name="net-framework-equivalent"></a>.NET Framework의 해당 값  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [예외 처리 루틴](../../c-runtime-library/exception-handling-routines.md)   
 [set_terminate](../../c-runtime-library/reference/set-terminate-crt.md)   
 [set_unexpected](../../c-runtime-library/reference/set-unexpected-crt.md)   
 [terminate](../../c-runtime-library/reference/terminate-crt.md)   
 [unexpected](../../c-runtime-library/reference/unexpected-crt.md)
