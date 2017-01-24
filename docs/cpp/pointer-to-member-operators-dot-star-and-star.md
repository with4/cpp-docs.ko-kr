---
title: "멤버 포인터 연산자: .* 및 -&gt;* | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - ".*"
  - "->*"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".* 연산자"
  - "->* 연산자"
  - "식[C++], 연산자"
  - "식[C++], 포인터"
  - "멤버 포인터 연산자"
ms.assetid: 2632be3f-1c81-4523-b56c-982a92a68688
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 멤버 포인터 연산자: .* 및 -&gt;*
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 구문  
  
```  
  
      expression .* expression  
expression –>* expression  
```  
  
## 설명  
 멤버 포인터 연산자\(.\* 및 –\>\*\)는 식의 왼쪽에 지정된 개체에 대한 특정 클래스 멤버의 값을 반환합니다.  오른쪽에는 클래스 멤버를 지정해야 합니다.  다음 예제에서는 이러한 연산자를 사용하는 방법을 보여 줍니다.  
  
```  
// expre_Expressions_with_Pointer_Member_Operators.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
  
class Testpm {  
public:  
   void m_func1() { cout << "m_func1\n"; }  
   int m_num;  
};  
  
// Define derived types pmfn and pmd.  
// These types are pointers to members m_func1() and  
// m_num, respectively.  
void (Testpm::*pmfn)() = &Testpm::m_func1;  
int Testpm::*pmd = &Testpm::m_num;  
  
int main() {  
   Testpm ATestpm;  
   Testpm *pTestpm = new Testpm;  
  
// Access the member function  
   (ATestpm.*pmfn)();  
   (pTestpm->*pmfn)();   // Parentheses required since * binds  
                        // less tightly than the function call.  
  
// Access the member data  
   ATestpm.*pmd = 1;  
   pTestpm->*pmd = 2;  
  
   cout  << ATestpm.*pmd << endl  
         << pTestpm->*pmd << endl;  
   delete pTestpm;  
}  
```  
  
## Output  
  
```  
m_func1  
m_func1  
1  
2  
```  
  
 앞의 예제에서는 멤버 함수 `m_func1`을 호출하기 위해 `pmfn` 멤버에 대한 포인터가 사용되었습니다.  또 다른 멤버 포인터, `pmd`는 `m_num` 멤버에 액세스하는 데 사용됩니다.  
  
 .\* 이항 연산자는 첫 번째 피연산자\(반드시 클래스 형식의 개체\)와 두 번째 피연산자\(반드시 멤버 포인터 형식\)를 결합합니다.  
  
 –\>\* 이항 연산자는 첫 번째 피연산자\(반드시 클래스 형식의 개체 포인터\)와 두 번째 피연산자\(반드시 멤버 포인터 형식\)를 결합합니다.  
  
 .\* 연산자가 포함된 식에서 첫 번째 피연산자는 두 번째 피연산자에 지정된 멤버 포인터의 클래스 형식이면서 해당 멤버 포인터에 액세스할 수 있거나 해당 클래스에서 명확히 파생되고 해당 클래스에 액세스할 수 있는 형식이어야 합니다.  
  
 –\>\* 연산자가 포함된 식에서 첫 번째 피연산자는 두 번째 피연산자에 지정된 형식의 "클래스 형식 포인터" 형식이거나 해당 클래스에서 명확히 파생된 형식이어야 합니다.  
  
## 예제  
 다음 클래스와 프로그램 부분을 살펴보십시오.  
  
```  
// expre_Expressions_with_Pointer_Member_Operators2.cpp  
// C2440 expected  
class BaseClass {  
public:  
   BaseClass(); // Base class constructor.  
   void Func1();  
};  
  
// Declare a pointer to member function Func1.  
void (BaseClass::*pmfnFunc1)() = &BaseClass::Func1;  
  
class Derived : public BaseClass {  
public:  
   Derived();  // Derived class constructor.  
   void Func2();  
};  
  
// Declare a pointer to member function Func2.  
void (Derived::*pmfnFunc2)() = &Derived::Func2;  
  
int main() {  
   BaseClass ABase;  
   Derived ADerived;  
  
   (ABase.*pmfnFunc1)();   // OK: defined for BaseClass.  
   (ABase.*pmfnFunc2)();   // Error: cannot use base class to  
                           // access pointers to members of  
                           // derived classes.   
  
   (ADerived.*pmfnFunc1)();   // OK: Derived is unambiguously  
                              // derived from BaseClass.   
   (ADerived.*pmfnFunc2)();   // OK: defined for Derived.  
}  
```  
  
 .\* 또는 –\>\* 멤버 포인터 연산자의 결과는 멤버 포인터 선언에 지정된 형식의 개체 또는 함수입니다.  따라서 앞의 예제에서 `ADerived.*pmfnFunc1()` 식의 결과는 void를 반환하는 함수 포인터입니다.  두 번째 피연산자가 l\-value인 경우 이 결과는 l\-value입니다.  
  
> [!NOTE]
>  멤버 포인터 연산자 중 하나의 결과가 함수인 경우 결과는 함수 호출 연산자에 대한 피연산자로만 사용할 수 있습니다.  
  
## 참고 항목  
 [C\+\+ 연산자](../misc/cpp-operators.md)   
 [C\+\+ 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)