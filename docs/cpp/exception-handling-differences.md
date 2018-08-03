---
title: 예외 처리 차이점 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- structured exception handling [C++], vs. C++ exception handling
- structured exception handling [C++], vs. unstructured
- exceptions [C++], wrapper class
- C++ exception handling [C++], vs. structured exception handling
- wrapper classes [C++], C exception
ms.assetid: f21d1944-4810-468e-b02a-9f77da4138c9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b9c17c0abbd8286d05423ac52abc2e2109253f6d
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39404625"
---
# <a name="exception-handling-differences"></a>예외 처리 차이점
c + + 예외 처리 모델은 여러 형식 다룬다는 하면서 C 구조적된 예외 처리 모델 처리 한 형식의 예외를 사용 하 여 구조적된 예외 처리 및 c + + 예외 처리의 주요 차이점은, 특히  **부호 없는 int**합니다. 즉, C 예외는 부호 없는 정수 값으로 식별되지만 C++ 예외는 데이터 형식으로 식별됩니다. C에서 예외가 발생하는 경우 각각의 가능한 처리기는 C 예외 컨텍스트를 조사하고 예외를 허용할지, 다른 처리기로 전달할지 아니면 무시할지를 결정하는 필터를 실행합니다. C++에서 예외가 발생하는 경우 예외는 어떤 형식이든 가능합니다.  
  
 두 번째 차이점으로, 예외가 정상적인 제어 흐름에 부차적으로 발생한다는 점에서 C 구조적 예외 처리 모델을 "비동기"라고 합니다. C++ 예외 처리 메커니즘은 완전히 "동기"입니다. 즉, 예외는 throw될 때만 발생합니다.  
  
 C + + 또는 연결 된 해당 필터를 사용 하 여 구조적된 예외 처리기에서 처리할 수 C 예외가 c + + 프로그램에서 발생 하는 경우 **catch** 처리기 중 더 동적으로 가깝기 예외 컨텍스트입니다. 다음 c + + 프로그램은 c + + 내에서 C 예외를 발생 하는 예를 들어 **시도** 컨텍스트:  
  
## <a name="example"></a>예  
  
```cpp 
// exceptions_Exception_Handling_Differences.cpp  
// compile with: /EHa  
#include <iostream>  
  
using namespace std;  
void SEHFunc( void );  
  
int main() {  
   try {  
      SEHFunc();  
   }  
   catch( ... ) {  
      cout << "Caught a C exception."<< endl;  
   }  
}  
  
void SEHFunc() {  
   __try {  
      int x, y = 0;  
      x = 5 / y;  
   }  
   __finally {  
      cout << "In finally." << endl;  
   }  
}  
```  
  
```Output  
In finally.  
Caught a C exception.  
```  
  
##  <a name="_core_c_exception_wrapper_class"></a> C 예외 래퍼 클래스  
 위와 같은 간단한 예제에서는 C 예외는 줄임표 (...)에 의해서만 낼 수 있습니다 (**...** ) **catch** 처리기입니다. 예외의 형식이나 특성에 대한 정보가 처리기로 전달되지 않습니다. 이 메서드가 작동하는 동안 각 C 예외가 특정 클래스에 연결되도록 두 가지 예외 처리 모델 간에 변형을 정의해야 하는 경우가 있습니다. 이렇게 하려면 C 예외에 특정 클래스 형식을 특성으로 지정하기 위해 사용하거나 파생시킬 수 있는 C 예외 "래퍼" 클래스를 정의할 수 있습니다. 이렇게 함으로써 각 C 예외가 c + +에서 처리 수 **catch** 처리기 보다 개별적으로 앞의 예제입니다.  
  
 래퍼 클래스에는 예외 값을 결정하는 멤버 함수로 구성되며 C 예외 모델에서 제공하는 확장된 예외 컨텍스트 정보에 액세스하는 인터페이스가 있을 수 있습니다. 기본 생성자 및 허용 하는 생성자를 정의할 수도 있습니다는 **부호 없는 int** 인수 (기본 C 예외 표현을 위해 제공), 및 비트 복사 생성자입니다. 다음은 가능한 C 예외 래퍼 클래스의 구현입니다.  
  
```cpp 
// exceptions_Exception_Handling_Differences2.cpp  
// compile with: /c  
class SE_Exception {  
private:  
   SE_Exception() {}  
   SE_Exception( SE_Exception& ) {}  
   unsigned int nSE;  
public:  
   SE_Exception( unsigned int n ) : nSE( n ) {}  
   ~SE_Exception() {}  
   unsigned int getSeNumber() {  
      return nSE;  
   }  
};  
```  
  
 이 클래스를 사용하려면 C 예외가 throw될 때마다 내부 예외 처리 메커니즘을 통해 호출되는 사용자 지정 C 예외 변환 함수를 설치합니다. 변환 함수 내에서 모든 형식의 예외를 throw 할 수 있습니다 (아마도 `SE_Exception` 에서 파생 된 형식 또는 클래스 형식 `SE_Exception`)를 적절 한 일치 하는 c + +에서 낼 수 있습니다 **catch** 처리기입니다. 변환 함수는 반환되기만 할 수 있으며, 이는 예외를 처리하지 않았음을 나타냅니다. 변환 함수 자체 C 예외를 발생 시키면 [종료](../c-runtime-library/reference/terminate-crt.md) 라고 합니다.  
  
 사용자 지정 변환 함수를 지정 하려면 호출을 [_set_se_translator](../c-runtime-library/reference/set-se-translator.md) 단일 인수로 변환 함수의 이름 사용 하 여 함수입니다. 작성 하는 변환 함수에 있는 스택의 각 함수 호출에 대해 한 번씩 호출 됩니다 **시도** 블록입니다. 기본 변환 함수가 없는; 호출 하 여 하나를 지정 하지 않는 경우 `_set_se_translator`, C 예외는 줄임표로만 낼 수 있습니다 **catch** 처리기입니다.  
  
## <a name="example"></a>예  
 예를 들어 다음 코드에서는 사용자 지정 변환 함수를 설치한 후 `SE_Exception` 클래스로 래핑된 C 예외를 발생시킵니다.  
  
```cpp 
// exceptions_Exception_Handling_Differences3.cpp  
// compile with: /EHa  
#include <stdio.h>  
#include <eh.h>  
#include <windows.h>  
  
class SE_Exception {  
private:  
   SE_Exception() {}  
   unsigned int nSE;  
  
public:  
   SE_Exception( SE_Exception& e) : nSE(e.nSE) {}  
   SE_Exception(unsigned int n) : nSE(n) {}  
   ~SE_Exception() {}  
   unsigned int getSeNumber() { return nSE; }  
};  
  
void SEFunc() {  
   __try {  
      int x, y = 0;  
      x = 5 / y;  
    }  
    __finally {  
      printf_s( "In finally\n" );  
   }  
}  
  
void trans_func( unsigned int u, _EXCEPTION_POINTERS* pExp ) {  
   printf_s( "In trans_func.\n" );  
   throw SE_Exception( u );  
}  
  
int main() {  
   _set_se_translator( trans_func );  
    try {  
      SEFunc();  
    }  
    catch( SE_Exception e ) {  
      printf_s( "Caught a __try exception with SE_Exception.\n" );  
      printf_s( "nSE = 0x%x\n", e.getSeNumber() );  
    }  
}  
```  
  
```Output  
In trans_func.  
In finally  
Caught a __try exception with SE_Exception.  
nSE = 0xc0000094  
```  
  
## <a name="see-also"></a>참고자료  
 [C(구조적) 및 C++ 예외 혼합](../cpp/mixing-c-structured-and-cpp-exceptions.md)