---
title: "예외 처리 차이점 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C++ 예외 처리, 구조적 예외 처리와 비교"
  - "예외, 래퍼 클래스"
  - "구조적 예외 처리, C++ 예외 처리와 비교"
  - "구조적 예외 처리, 비구조적 방식과 비교"
  - "래퍼 클래스, C 예외"
ms.assetid: f21d1944-4810-468e-b02a-9f77da4138c9
caps.latest.revision: 11
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 예외 처리 차이점
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

구조적 예외 처리와 C\+\+ 예외 처리의 가장 큰 차이점은 C 구조적 예외 처리 모델은 한 형식\(`unsigned int`\)의 예외만 처리하는 반면에 C\+\+ 예외 처리 모델은 여러 형식을 다룬다는 점입니다.  즉, C 예외는 부호 없는 정수 값으로 식별되지만 C\+\+ 예외는 데이터 형식으로 식별됩니다.  C에서 예외가 발생하는 경우 각각의 가능한 처리기는 C 예외 컨텍스트를 조사하고 예외를 허용할지, 다른 처리기로 전달할지 아니면 무시할지를 결정하는 필터를 실행합니다.  C\+\+에서 예외가 발생하는 경우 예외는 어떤 형식이든 가능합니다.  
  
 두 번째 차이점으로, 예외가 정상적인 제어 흐름에 부차적으로 발생한다는 점에서 C 구조적 예외 처리 모델을 "비동기"라고 합니다.  C\+\+ 예외 처리 메커니즘은 완전히 "동기"입니다. 즉, 예외는 throw될 때만 발생합니다.  
  
 C\+\+ 프로그램에서 C 예외가 발생하는 경우, 관련 필터를 사용하는 구조적 예외 처리기와 C\+\+ **catch** 처리기 중에서 예외 컨텍스트에 동적으로 보다 가까운 처리기가 해당 예외를 처리할 수 있습니다.  예를 들어 다음 C\+\+ 프로그램은 C\+\+ **try** 컨텍스트 내부에서 C 예외를 발생시킵니다.  
  
## 예제  
  
```  
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
  
  **In finally.**  
**Caught a C exception.**   
##  <a name="_core_c_exception_wrapper_class"></a> C 예외 래퍼 클래스  
 위와 같은 간단한 예제에서 C 예외는 줄임표\(**...**\) **catch** 처리기로만 catch할 수 있습니다.  예외의 형식이나 특성에 대한 정보가 처리기로 전달되지 않습니다.  이 메서드가 작동하는 동안 각 C 예외가 특정 클래스에 연결되도록 두 가지 예외 처리 모델 간에 변환을 정의해야 하는 경우가 있습니다.  이렇게 하려면 C 예외에 특정 클래스 형식을 특성으로 지정하기 위해 사용하거나 파생시킬 수 있는 C 예외 "래퍼" 클래스를 정의할 수 있습니다.  이렇게 함으로써 각 C 예외는 이전 예제보다 개별적으로 C\+\+ **catch** 처리기로 처리될 수 있습니다.  
  
 래퍼 클래스에는 예외 값을 결정하는 멤버 함수로 구성되며 C 예외 모델에서 제공하는 확장된 예외 컨텍스트 정보에 액세스하는 인터페이스가 있을 수 있습니다.  기본 생성자와 `unsigned int` 인수\(기본 C 예외 표현을 위해 제공\)를 받아들이는 생성자 및 비트 복사 생성자를 정의하려고 할 수도 있습니다.  다음은 가능한 C 예외 래퍼 클래스의 구현입니다.  
  
```  
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
  
 이 클래스를 사용하려면 C 예외가 throw될 때마다 내부 예외 처리 메커니즘을 통해 호출되는 사용자 지정 C 예외 변환 함수를 설치합니다.  변환 함수 내에서 일치하는 적절한 C\+\+ **catch** 처리기로 catch될 수 있는 모든 형식의 예외\(예: `SE_Exception` 형식 또는 `SE_Exception`에서 파생된 클래스 형식\)를 throw할 수 있습니다.  변환 함수는 반환되기만 할 수 있으며, 이는 예외를 처리하지 않았음을 나타냅니다.  변환 함수 자체에서 C 예외를 발생시키는 경우 [terminate](../c-runtime-library/reference/terminate-crt.md)가 호출됩니다.  
  
 사용자 지정 변환 함수를 지정하려면 변환 함수의 이름을 단일 인수로 사용하여 [\_set\_se\_translator](../c-runtime-library/reference/set-se-translator.md) 함수를 호출합니다.  사용자가 작성하는 변환 함수는 **try** 블록이 있는 스택의 각 함수 호출에 대해 한 번씩 호출됩니다.  기본 변환 함수는 없으며, `_set_se_translator`를 호출하여 변환 함수를 지정하지 않는 경우 C 예외는 줄임표 **catch** 처리기로만 catch될 수 있습니다.  
  
## 예제  
 예를 들어 다음 코드에서는 사용자 지정 변환 함수를 설치한 후 `SE_Exception` 클래스로 래핑된 C 예외를 발생시킵니다.  
  
```  
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
  
  **In trans\_func.**  
**In finally**  
**Caught a \_\_try exception with SE\_Exception.**  
**nSE \= 0xc0000094**   
## 참고 항목  
 [\(구조적\) C 및 C\+\+ 예외 혼합](../cpp/mixing-c-structured-and-cpp-exceptions.md)