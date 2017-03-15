---
title: "기본 식 | Microsoft Docs"
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
  - "식[C++], 리터럴"
  - "식[C++], name"
  - "식[C++], 기본"
  - "식[C++], 정규화된 이름"
  - "기본 식"
ms.assetid: 8ef9a814-6058-4b93-9b6e-e8eb8350b1ca
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 기본 식
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

기본 식은 더 복잡한 식의 구성 요소이며  리터럴, 이름 및 범위 결정 연산자\(`::`\)로 정규화된 이름입니다.  기본 식의 형식은 다음 중 하나입니다.  
  
```  
  
        literal  
this  
:: name  
name   
( expression )  
```  
  
 리터럴은 상수 기본 식입니다.  지정의 형태에 따라 형식이 결정됩니다.  리터럴 지정에 대한 자세한 내용은 [리터럴](../cpp/numeric-boolean-and-pointer-literals-cpp.md)을 참조하십시오.  
  
 **this** 키워드는 클래스 개체의 포인터로서  비정적 멤버 함수 안에 사용할 수 있으며 함수가 호출된 인스턴스에 대한 클래스의 인스턴스를 가리킵니다.  클래스 멤버 함수 본문 밖에서 **this** 키워드를 사용할 수 없습니다.  
  
 **this** 포인터의 형식은 `type` **\*const**\(`type`은 클래스 이름\)이며 특별히 **this** 포인터를 수정하지 않고 함수 안에 포함됩니다.  다음 예제에서는 멤버 함수 선언과 **this**의 형식을 보여 줍니다.  
  
```  
// expre_Primary_Expressions.cpp  
// compile with: /LD  
class Example  
{  
public:  
    void Func();          //  * const this  
    void Func() const;    //  const * const this  
    void Func() volatile; //  volatile * const this  
};  
```  
  
 **this** 포인터의 형식 수정에 대한 자세한 내용은 [this 포인터의 형식](../misc/type-of-this-pointer.md)을 참조하십시오.  
  
 이름 앞의 범위 결정 연산자\(`::`\)는 기본 식을 구성합니다.  이러한 이름은 멤버 이름이 아니라 전역 범위의 이름이어야 합니다.  이름의 선언이 이 식의 형식을 결정합니다.  선언 이름이 l\-value인 경우 l\-value이므로 대입 연산자 식의 왼쪽에 나타날 수 있습니다.  범위 결정 연산자를 사용하면 전역 이름이 현재 범위에서 숨겨지더라도 해당 이름이 참조됩니다.  범위 결정 연산자를 사용하는 방법의 예는 [범위](../cpp/scope-visual-cpp.md)를 참조하십시오.  
  
 괄호로 묶은 식은 그 형식과 값이 괄호로 묶지 않은 식과 동일한 기본 식입니다.  괄호로 묶지 않은 식이 l\-value일 경우 l\-value입니다.  
  
 위에 주어진 기본 식 구문의 컨텍스트에서는 이름 앞에 범위 결정 연산자를 사용할 때 클래스 안에 올 수 있는 이름의 형식이 허용되지 않더라도 *name*은 [이름](http://msdn.microsoft.com/ko-kr/1c49cc24-08d5-4884-b170-ba8ed42d80db)에 대해 설명된 구문의 항목을 의미합니다.  사용자 정의 변환 함수 이름과 소멸자 이름이 여기에 포함됩니다.  
  
 기본 식의 예제는 다음과 같습니다.  
  
```  
100 // literal  
'c' // literal  
this // in a member function, a pointer to the class instance  
::func // a global function  
::operator + // a global operator function  
::A::B // a global qualified name  
( i + 1 ) // a parenthesized expression  
```  
  
 아래의 예제는 모두 이름으로 간주되므로 여러 가지 형식의 기본 식입니다.  
  
```  
MyClass // a identifier  
MyClass::f // a qualified name  
operator = // an operator function name  
operator char* // a conversion operator function name  
~MyClass // a destructor name  
A::B   // a qualified name  
A<int> // a template id  
```  
  
## 참고 항목  
 [식의 형식](../cpp/types-of-expressions.md)