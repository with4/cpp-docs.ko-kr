---
title: "typeid 연산자 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "typeid 연산자"
ms.assetid: 8871cee6-d6b9-4301-a5cb-bf3dc9798d61
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# typeid 연산자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 구문  
  
```  
  
      typeid(   
      type-id  
       )  
typeid( expression )  
```  
  
## 설명  
 `typeid` 연산자를 사용하면 런타임에 개체 형식이 결정됩니다.  
  
 `typeid`의 결과는 **const type\_info&**입니다.  사용하는 `typeid` 형식에 따라 *type\-id* 또는 *expression*의 형식을 나타내는 **type\_info** 개체에 대한 참조가 값입니다.  자세한 내용은 [type\_info 클래스](../cpp/type-info-class.md)를 참조하십시오.  
  
 `typeid` 연산자는 관리되는 형식\(추상 선언자 또는 인스턴스\)에 사용되지 않습니다. 지정된 형식의 <xref:System.Type>을 구하는 데 대한 자세한 내용은 [typeid](../windows/typeid-cpp-component-extensions.md)를 참조하십시오.  
  
 `typeid` 연산자는 다형 클래스 형식의 l\-value에 적용될 때 런타임 검사를 하지 않습니다. 제공된 정적 정보로 개체의 true 형식을 확인할 수 없습니다.  다음과 같은 경우가 여기에 해당합니다.  
  
-   클래스에 대한 참조  
  
-   \*로 역참조되는 포인터  
  
-   첨자 포인터\(예: \[ \]\). 일반적으로 다형 형식의 포인터에 첨자를 사용하는 것은 안전하지 않습니다.  
  
 *expression*이 기본 클래스를 가리지만 개체 형식이 실제로 기본 클래스에서 파생된 경우 결과는 파생된 클래스의 **type\_info** 참조입니다.  *expression*은 다형 형식\(가상 함수가 있는 클래스\)을 가리켜야 합니다.  그렇지 않으면 결과는 *expression*에서 참조되는 정적 클래스의 **type\_info**입니다.  또한 가리키는 개체를 사용하도록 포인터를 역참조해야 합니다.  포인터를 역참조하지 않으면 가리키는 대상이 아니라 포인터의 **type\_info**가 결과가 됩니다.  예를 들면 다음과 같습니다.  
  
```  
// expre_typeid_Operator.cpp  
// compile with: /GR /EHsc  
#include <iostream>  
#include <typeinfo.h>  
  
class Base {  
public:  
   virtual void vvfunc() {}  
};  
  
class Derived : public Base {};  
  
using namespace std;  
int main() {  
   Derived* pd = new Derived;  
   Base* pb = pd;  
   cout << typeid( pb ).name() << endl;   //prints "class Base *"  
   cout << typeid( *pb ).name() << endl;   //prints "class Derived"  
   cout << typeid( pd ).name() << endl;   //prints "class Derived *"  
   cout << typeid( *pd ).name() << endl;   //prints "class Derived"  
   delete pd;  
}  
```  
  
 *expression*이 포인터를 역참조하고 포인터의 값이 0이면  **typeid**가 [bad\_typeid exception](../cpp/bad-typeid-exception.md)을 throw합니다.  포인터가 유효한 개체를 가리키지 않을 경우 `__non_rtti_object` 예외가 throw되며, 개체가 유효하지 않으므로\(잘못된 포인터 또는 [\/GR](../build/reference/gr-enable-run-time-type-information.md)을 사용하여 코드를 컴파일하지 않음\) 코드가 액세스 위반 등의 오류를 트리거한 RTTI를 분석하려는 시도를 나타냅니다.  
  
 *expression*이 개체의 기본 클래스에 대한 포인터도 아니고 참조도 아닐 경우 *expression*의 정적 형식을 나타내는 **type\_info** 참조가 결과입니다.  식의 정적 형식은 컴파일 타임에 알려지는 식의 형식을 참조합니다.  식의 정적 형식을 평가할 때 식의 의미 체계가 무시됩니다.  또한 식의 정적 형식을 결정할 때 가능할 경우 참조가 무시됩니다.  
  
```  
// expre_typeid_Operator_2.cpp  
#include <typeinfo>  
  
int main()  
{  
   typeid(int) == typeid(int&); // evaluates to true  
}  
```  
  
 **typeid**를 템플릿에 사용하여 템플릿 매개 변수의 형식을 확인할 수도 있습니다.  
  
```  
// expre_typeid_Operator_3.cpp  
// compile with: /c  
#include <typeinfo>  
template < typename T >   
T max( T arg1, T arg2 ) {  
   cout << typeid( T ).name() << "s compared." << endl;  
   return ( arg1 > arg2 ? arg1 : arg2 );  
}  
```  
  
## 참고 항목  
 [런타임 형식 정보](../cpp/run-time-type-information.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)