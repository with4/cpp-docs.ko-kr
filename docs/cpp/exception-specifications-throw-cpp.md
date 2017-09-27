---
title: "예외 사양 (throw) (c + +) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- exceptions, exception specifications
- throwing exceptions, throw keyword
- C++ exception handling, throwing exceptions
- throw keyword [C++], throw() vs. throw(...)
- throw keyword [C++], exception specifications
ms.assetid: 4d3276df-6f31-4c7f-8cab-b9d2d003a629
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 6577cf489ee1c9d64689938bb8a12660cec96893
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="exception-specifications-throw-noexcept-c"></a>예외 사양 (throw, noexcept) (c + +)
예외 사양은 함수에 의해 전파 될 수 있는 예외 형식에 대해 프로그래머의 의도 표시 하는 c + + 언어 기능. 하는 함수 되거나 예외를 사용 하 여 종료 되지 않을 지정할 수는 *예외 사양이*합니다. 컴파일러는 함수에 대 한 호출을 최적화 하기 위해이 정보를 사용 하 고 예외가 발생된 하는 경우 프로그램을 종료 하려면 함수를 이스케이프 합니다. 예외 사양는 다음과 같은 두 종류가 있습니다. *noexcept 사양* 새로운 C + + 11 기능입니다. 함수를 이스케이프 될 수 있는 잠재적인 예외 집합이 비어 있는지 여부를 지정 합니다. *동적 예외 사양은*, 또는 `throw(optional_type_list)` C + + 11에서 사용 되지 않는 사양과 Visual Studio에서 부분적 으로만 지원 됩니다. 이 예외 사양은 함수에서 예외를 throw 할 수 하는 방법에 대 한 요약 정보를 제공 하는데 실제로 문제가 있는 것으로 발견 된 합니다. 어느 정도 유용한 것으로 입증 된 하나의 동적 예외 사양을는 무조건 `throw()` 사양입니다. 예를 들어 함수 선언 합니다.  
  
```cpp  
void MyFunction(int i) throw();  
```  
  
 컴파일러에 함수가 아무 예외도 throw하지 않음을 알립니다. 사용 하 여 동일 [__declspec (nothrow)](../cpp/nothrow-cpp.md)합니다. 이 예외 사양 사용은 옵션입니다.  
  
ISO C + + 11 표준에는 [noexcept](../cpp/noexcept-cpp.md) 연산자를 대체 값으로 도입 되었습니다. Visual Studio 2015 이상에서 지원 됩니다. 사용 가능한 경우 항상는 `noexcept` 함수 예외가 throw 될 가능성이 있는지 여부를 지정 하는 식입니다. 예를 들어 위의 대신이 함수 선언을 사용 합니다.  
  
```cpp  
void MyFunction(int i) noexcept;  
```  
  
Visual c + +에서 완벽 하 게 지원 하지만 `noexcept` 동적 예외 사양은 구현에서 ISO c + + 표준에서 필수 식입니다.  다음 표에는 예외 사양의 Visual C++ 구현이 요약되어 있습니다.  
  
|예외 사양|의미|  
|-----------------------------|-------------|  
|`noexcept`<br/>`noexcept(true)`<br/>`throw()`|이 함수는 예외를 throw하지 않습니다. 그러나 표시 된 함수에서 예외가 발생 하는 경우 `throw()`, Visual c + + 컴파일러 호출 `std::terminate`이 아니라 `std::unexpected`합니다. 참조 [std::unexpected](../c-runtime-library/reference/unexpected-crt.md) 자세한 정보에 대 한 합니다. 함수 표시 되 면 `noexcept`, `noexcept(true)`, 또는 `throw()`, Visual c + + 컴파일러에 함수가 c + + 예외를 throw 하지 않습니다 및 그에 따라 코드를 생성 한다고 가정 합니다. 코드 최적화 함수는 함수는 예외를 throw 하는 경우 c + + 예외를 throw 하지 않습니다 가정을 기반으로 c + + 컴파일러에 의해 수행 될 수 있습니다, 때문에 프로그램이 제대로 실행 되지 않을 수 있습니다.|  
|`noexcept(false)`<br/>`throw(...)`<br/>사양이 없는|함수는 모든 형식의 예외를 throw 할 수 있습니다.|  
|`throw(type)`|함수는 `type` 형식의 예외를 throw할 수 있습니다. Visual c + +에서는이 구문을 허용 되지만로 해석 되 `noexcept(false)`합니다.|  
  
 예외 처리 응용 프로그램을 사용 하는 함수에에서 있어야 함수 외부 범위를 종료 하기 전에 예외를 throw 하는 핸들을 표시 하는 호출 스택을 `noexcept`, `noexcept(true)`, 또는 `throw()`합니다. 예외를 throw 하 한 및 예외를 처리 하는 것으로 지정 된 함수 사이 호출 하는 경우 `noexcept`, `noexcept(true)`, 또는 `throw()`, 프로그램 고 noexcept 함수가 예외를 전파 될 때 종료 됩니다.  
  
 예외 동작 함수는 다음 요인에 따라 달라 집니다.  
  
-   C 또는 C++에서 함수를 컴파일하는지 여부  
  
-   [/EH](../build/reference/eh-exception-handling-model.md) 컴파일러 옵션을 사용 합니다.  
  
-   예외 사양을 명시적으로 지정하는지 여부  
  
 C 함수에서는 명시적 예외 사양이 허용되지 않습니다. C 함수 아닌 것으로 가정에서 예외를 throw **/EHsc**, 아래에서 구조화 된 예외를 throw 할 수 있습니다 및 **/EHs**, **/EHa**, 또는 **/EHac**합니다.  
  
 다음 표에서 c + + 함수는 다양 한 컴파일러 예외 처리 옵션 아래에서 잠재적으로 throw 할 수 있습니다 하는 여부가 요약 되어 있습니다.  
  
|함수|/EHsc|/EHs|/EHa|/EHac|  
|--------------|------------|-----------|-----------|------------|  
|예외 사양이 없는 C++ 함수|예|예|예|예|  
|C + + 함수 `noexcept`, `noexcept(true)`, 또는 `throw()` 예외 사양|아니요|아니요|예|예|  
|C + + 함수 `noexcept(false)`, `throw(...)`, 또는 `throw(type)` 예외 사양|예|예|예|예|  
  
## <a name="example"></a>예제  
  
```cpp  
// exception_specification.cpp  
// compile with: /EHs  
#include <stdio.h>  
  
void handler() {  
   printf_s("in handler\n");  
}  
  
void f1(void) throw(int) {  
   printf_s("About to throw 1\n");  
   if (1)  
      throw 1;  
}  
  
void f5(void) throw() {  
   try {  
      f1();  
   }  
   catch(...) {  
      handler();  
    }  
}  
  
// invalid, doesn't handle the int exception thrown from f1()  
// void f3(void) throw() {  
//   f1();  
// }  
  
void __declspec(nothrow) f2(void) {  
   try {  
      f1();  
   }  
   catch(int) {  
      handler();  
    }  
}  
  
// only valid if compiled without /EHc   
// /EHc means assume extern "C" functions don't throw exceptions  
extern "C" void f4(void);  
void f4(void) {  
   f1();  
}  
  
int main() {  
   f2();  
  
   try {  
      f4();  
   }  
   catch(...) {  
      printf_s("Caught exception from f4\n");  
   }  
   f5();  
}  
```  
  
```Output  
About to throw 1  
in handler  
About to throw 1  
Caught exception from f4  
About to throw 1  
in handler  
```  
  
## <a name="see-also"></a>참고 항목  
 [try, throw 및 catch 문(C++)](../cpp/try-throw-and-catch-statements-cpp.md)   
 [C++ 예외 처리](../cpp/cpp-exception-handling.md)
