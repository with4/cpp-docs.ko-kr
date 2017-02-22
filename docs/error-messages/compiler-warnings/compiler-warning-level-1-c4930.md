---
title: "컴파일러 경고 (수준 1) C4930 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4930"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4930"
ms.assetid: 89a206c9-c536-4186-8e81-1cde3e7f4f5b
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# 컴파일러 경고 (수준 1) C4930
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'prototype': 프로토타입 함수가 호출되지 않았습니다. 변수 정의로 사용하려고 한 것은 아닌지 확인하십시오.  
  
 컴파일러에서 사용되지 않은 함수 프로토타입을 발견했습니다.  프로토타입을 변수 정의로 사용하려면 여는 괄호와 닫는 괄호를 제거하십시오.  
  
 다음 샘플에서는 C4930 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4930.cpp  
// compile with: /W1  
class Lock {  
public:  
   int i;  
};  
  
void f() {  
   Lock theLock();   // C4930  
   // try the following line instead  
   // Lock theLock;  
}  
  
int main() {  
}  
```  
  
 C4930 경고는 컴파일러에서 함수 프로토타입 선언과 함수 호출을 구별할 수 없는 경우에도 발생할 수 있습니다.  
  
 다음 샘플에서는 C4930 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4930b.cpp  
// compile with: /EHsc /W1  
  
class BooleanException  
{  
   bool _result;  
  
public:  
   BooleanException(bool result)  
      : _result(result)  
   {  
   }  
  
   bool GetResult() const  
   {  
      return _result;  
   }  
};  
  
template<class T = BooleanException>  
class IfFailedThrow  
{  
public:  
   IfFailedThrow(bool result)  
   {  
      if (!result)  
      {  
         throw T(result);  
      }  
   }  
};  
  
class MyClass  
{  
public:  
   bool MyFunc()  
   {  
      try  
      {  
         IfFailedThrow<>(MyMethod()); // C4930  
  
         // try one of the following lines instead  
         // IfFailedThrow<> ift(MyMethod());  
         // IfFailedThrow<>(this->MyMethod());  
         // IfFailedThrow<>((*this).MyMethod());  
  
         return true;  
      }  
      catch (BooleanException e)  
      {  
         return e.GetResult();  
      }  
   }  
  
private:  
   bool MyMethod()  
   {  
      return true;  
   }  
};  
  
int main()  
{  
   MyClass myClass;  
   myClass.MyFunc();  
}  
```  
  
 위 샘플에서는 인수를 받지 않는 메서드의 결과가 이름이 없는 로컬 클래스 변수의 생성자에 인수로 전달됩니다.  이 호출을 명확하게 하려면 로컬 변수에 이름을 지정하거나 개체 인스턴스와 적절한 pointer\-to\-member 연산자를 사용하여 메서드 호출에 접두사를 지정합니다.