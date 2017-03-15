---
title: "예외 사양(throw)(C++) | Microsoft Docs"
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
  - "C++ 예외 처리, 예외 throw"
  - "예외, 예외 사양"
  - "throw 키워드[C++], 예외 사양"
  - "throw 키워드[C++], throw()와 throw(...) 비교"
  - "예외 throw, throw 키워드"
ms.assetid: 4d3276df-6f31-4c7f-8cab-b9d2d003a629
caps.latest.revision: 20
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 예외 사양(throw)(C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

예외 사양은 C\+\+11에서 사용되지 않는 C\+\+ 언어 기능으로서,  함수에서 throw할 수 있는 예외에 대한 요약 정보를 제공하도록 설계되었으나 실제로는 문제가 있는 것으로 확인되었습니다.  어느 정도 유용한 것으로 입증된 한 가지 예외 사양은 throw\(\) 사양이었습니다.  예:  
  
```  
void MyFunction(int i) throw();  
```  
  
 컴파일러에 함수가 아무 예외도 throw하지 않음을 알립니다.  이는 [\_\_declspec\(nothrow\)](../cpp/nothrow-cpp.md)를 사용하는 것과 같습니다.  이 예외 사양 사용은 옵션입니다.  
  
 **\(C\+\+11\)** ISO C\+\+11 표준에서 [noexcept](../cpp/noexcept-cpp.md) 연산자가 도입되었으며 Visual Studio 2015 이상에서 지원됩니다.  가능한 경우 언제나 `noexcept`를 사용하여 함수가 예외를 throw할 수 있는지 여부를 지정합니다.  
  
 Visual C\+\+는 예외 사양을 구현할 때 ISO C\+\+ 표준을 사용합니다.  다음 표에는 예외 사양의 Visual C\+\+ 구현이 요약되어 있습니다.  
  
|예외 사양|의미|  
|-----------|--------|  
|throw\(\)|이 함수는 예외를 throw하지 않습니다.  그러나 throw\(\)로 표시된 함수에서 예외가 throw되는 경우 Visual C\+\+ 컴파일러는 unexpected를 호출하지 않습니다. 자세한 내용은 [unexpected](../c-runtime-library/reference/unexpected-crt.md) 및 [unexpected](../Topic/unexpected%20\(%3Cexception%3E\).md)를 참조하세요.  함수에 throw\(\)가 표시된 경우 Visual C\+\+ 컴파일러는 함수가 C\+\+ 예외를 throw하지 않고 그에 따라 코드를 생성한다고 가정합니다.  함수가 예외를 throw하는 경우 C\+\+ 컴파일러에서 수행할 수 있는 코드 최적화로 인해\(함수가 C\+\+ 예외를 throw하지 않는다는 가정을 전제\) 프로그램이 제대로 실행하지 못할 수 있습니다.|  
|throw\(...\)|함수는 예외를 throw할 수 있습니다.|  
|throw\(`type`\)|함수는 `type` 형식의 예외를 throw할 수 있습니다.  하지만 Visual C\+\+ .NET에서 이는 throw\(...\)로 해석됩니다.  [함수 예외 지정자](../misc/15-4-function-exception-specifiers.md)를 참조하세요.|  
  
 응용 프로그램에서 예외 처리를 사용하는 경우 throw된 예외를 처리하는 함수가 하나 이상 있어야 합니다.  예외를 throw하고 예외를 처리하는 함수 사이에서 호출되는 모든 함수는 예외를 throw할 수 있어야 합니다.  
  
 함수의 throw 동작은 다음과 같은 요소에 따라 달라집니다.  
  
-   C 또는 C\+\+에서 함수를 컴파일하는지 여부  
  
-   사용하는 [\/EH](../build/reference/eh-exception-handling-model.md) 컴파일러 옵션  
  
-   예외 사양을 명시적으로 지정하는지 여부  
  
 C 함수에서는 명시적 예외 사양이 허용되지 않습니다.  
  
 다음 표는 함수의 throw 동작을 요약합니다.  
  
|함수|\/EHsc|\/EHs|\/EHa|\/EHac|  
|--------|------------|-----------|-----------|------------|  
|C 함수|throw\(\)|throw\(...\)|throw\(...\)|throw\(...\)|  
|예외 사양이 없는 C\+\+ 함수|throw\(...\)|throw\(...\)|throw\(...\)|throw\(...\)|  
|throw\(\) 예외 사양이 있는 C\+\+ 함수|throw\(\)|throw\(\)|throw\(...\)|throw\(...\)|  
|throw\(...\) 예외 사양이 있는 C\+\+ 함수|throw\(...\)|throw\(...\)|throw\(...\)|throw\(...\)|  
|throw\(`type`\) 예외 사양이 있는 C\+\+ 함수|throw\(...\)|throw\(...\)|throw\(...\)|throw\(...\)|  
  
## 예제  
  
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
  
  **About to throw 1**  
**in handler**  
**About to throw 1**  
**Caught exception from f4**  
**About to throw 1**  
**in handler**   
## 참고 항목  
 [Try, Throw 및 Catch 문\(C\+\+\)](../cpp/try-throw-and-catch-statements-cpp.md)   
 [C\+\+ 예외 처리](../cpp/cpp-exception-handling.md)