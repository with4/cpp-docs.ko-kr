---
title: "비표준 동작 | Microsoft Docs"
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
  - "호환성 및 규격, 비표준 동작"
  - "Microsoft 전용, 컴파일러 동작"
  - "비표준 동작, 규격 및 호환성"
ms.assetid: a57dea27-dc79-4f64-8a83-017e84841773
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 비표준 동작
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 섹션은 Visual C\+\+ 구현이 C\+\+ 표준을 준수하지 않는 일부 알려진 장소를 나열합니다.  아래의 섹션 번호는 C\+\+ 11 표준\(ISO\/IEC 14882:2011\(E\)\)의 섹션 번호를 나타냅니다.  
  
 C\+\+ 표준과는 다른 컴파일러 한계 목록은 [컴파일러 한계](../cpp/compiler-limits.md)에 나와 있습니다.  
  
## 공변 반환 형식  
 가상 함수에 개수가 가변적인 인수가 있을 때 가상 기본 클래스는 공변\(covariant\) 반환 형식으로 지원되지 않습니다.  이것은 C\+\+ ISO 사양의 단원 10.3, 7항에 맞지 않습니다.  다음 샘플은 컴파일하지 않아 컴파일러 오류 [C2688](../error-messages/compiler-errors-2/compiler-error-c2688.md)가 생성됩니다.  
  
```cpp  
// CovariantReturn.cpp  
class A   
{  
   virtual A* f(int c, ...);   // remove ...  
};  
  
class B : virtual A  
{  
   B* f(int c, ...);   // C2688 remove ...  
};  
```  
  
## 템플릿에서 독립적인 이름 바인딩  
 Visual C\+\+ 컴파일러는 최초 템플릿 구문 분석 시 독립적인 이름 바인딩을 현재 지원하지 않습니다.  이것은 C\+\+ ISO 사양의 단원 14.6.3에 맞지 않습니다.  이로 인해 템플릿이 확인되고 인스턴스화되기 전에 오버로드가 선언될 수 있습니다.  
  
```cpp  
#include <iostream>  
using namespace std;  
  
namespace N {  
   void f(int) { cout << "f(int)" << endl;}  
}  
  
template <class T> void g(T) {  
    N::f('a');   // calls f(char), should call f(int)  
}  
  
namespace N {  
    void f(char) { cout << "f(char)" << endl;}  
}  
  
int main() {  
    g('c');  
}  
// Output: f(char)  
  
```  
  
## 함수 예외 지정자  
 `throw()` 이외의 함수 예외 지정자는 구문 분석되지만 사용되지 않습니다.  이것은 C\+\+ 사양의 단원 15.4에 맞지 않습니다.  예를 들면 다음과 같습니다.  
  
```cpp  
void f() throw(int); // parsed but not used  
void g() throw();    // parsed and used  
```  
  
 예외 사양에 대한 자세한 내용은 [예외 사양](../cpp/exception-specifications-throw-cpp.md)을 참조하십시오.  
  
## char\_traits::eof\(\)  
 C\+\+ 표준에서는 [char\_traits::eof](../Topic/char_traits::eof.md)가 올바른 `char_type` 값에 해당하면 안 됩니다.  Visual C\+\+ 컴파일러는 `wchar_t` 형식이 아니라 `char` 형식에 이 제약 조건을 적용합니다.  이것은 C\+\+ ISO 사양의 단원 12.1.1, 표 62의 요구 사항에 맞지 않습니다.  아래 예제에서는 이 작업을 보여 줍니다.  
  
```cpp  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
  
    char_traits<char>::int_type int2 = char_traits<char>::eof();  
    cout << "The eof marker for char_traits<char> is: " << int2 << endl;  
  
    char_traits<wchar_t>::int_type int3 = char_traits<wchar_t>::eof();  
    cout << "The eof marker for char_traits<wchar_t> is: " << int3 << endl;  
}  
```  
  
## 개체 저장소 위치  
 C\+\+ 표준\(단원 1.8, 6항\)에서는 전체 C\+\+ 개체에 고유한 저장소 위치가 있어야 합니다.  그러나 Visual C\+\+에서는 데이터 멤버가 없는 형식이 개체의 수명이 지속되는 동안 다른 형식과 저장소 위치를 공유하는 경우가 있습니다.