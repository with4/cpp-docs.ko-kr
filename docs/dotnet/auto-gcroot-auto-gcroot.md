---
title: "auto_gcroot::auto_gcroot | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "msclr::auto_gcroot::auto_gcroot"
  - "auto_gcroot::auto_gcroot"
  - "auto_gcroot.auto_gcroot"
  - "msclr.auto_gcroot.auto_gcroot"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "auto_gcroot::auto_gcroot"
ms.assetid: 27faa42a-64ea-4d31-836f-073a55145735
caps.latest.revision: 12
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# auto_gcroot::auto_gcroot
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`auto_gcroot` 생성자  
  
## 구문  
  
```  
auto_gcroot(  
   _element_type _ptr = nullptr  
);  
auto_gcroot(  
   auto_gcroot<_element_type> & _right  
);  
template<typename _other_type>  
auto_gcroot(  
   auto_gcroot<_other_type> & _right  
);  
```  
  
#### 매개 변수  
 `_ptr`  
 소유 개체입니다.  
  
 `_right`  
 기존 `auto_gcroot`입니다.  
  
## 설명  
 기존  `auto_gcroot` 으로부터  `auto_gcroot` 을 구성할 때, 기존  `auto_gcroot` 는 해당 개체를 새  `auto_gcroot` 에 개체의 소유권을 이전 하기 전에 해제합니다.  
  
## 예제  
  
```  
// msl_auto_gcroot_auto_gcroot.cpp  
// compile with: /clr  
#include <msclr\auto_gcroot.h>  
  
using namespace System;  
using namespace msclr;  
  
ref class RefClassA {  
protected:  
   String^ m_s;     
public:  
   RefClassA(String^ s) : m_s(s) {  
      Console::WriteLine( "in RefClassA constructor: " + m_s );  
   }  
   ~RefClassA() {  
      Console::WriteLine( "in RefClassA destructor: " + m_s );  
   }  
  
   virtual void PrintHello() {  
      Console::WriteLine( "Hello from {0} A!", m_s );  
   }  
};  
  
ref class RefClassB : RefClassA {  
public:     
   RefClassB( String^ s ) : RefClassA( s ) {}  
   virtual void PrintHello() new {  
      Console::WriteLine( "Hello from {0} B!", m_s );  
   }  
};  
  
class ClassA { //unmanaged class  
private:     
   auto_gcroot<RefClassA^> m_a;  
  
public:  
   ClassA() : m_a( gcnew RefClassA( "unmanaged" ) ) {}  
   ~ClassA() {} //no need to delete m_a  
  
   void DoSomething() {  
      m_a->PrintHello();  
   }  
};  
  
int main()  
{  
   {  
      ClassA a;  
      a.DoSomething();  
   } // a.m_a is automatically destroyed as a goes out of scope  
  
   {  
      auto_gcroot<RefClassA^> a(gcnew RefClassA( "first" ) );  
      a->PrintHello();  
   }  
  
   {  
      auto_gcroot<RefClassB^> b(gcnew RefClassB( "second" ) );  
      b->PrintHello();  
      auto_gcroot<RefClassA^> a(b); //construct from derived type  
      a->PrintHello();  
      auto_gcroot<RefClassA^> a2(a); //construct from same type  
      a2->PrintHello();  
   }  
  
   Console::WriteLine("done");  
}  
```  
  
  **RefClassA 생성자에서: 관리되지 않는**  
**안녕 관리되지 않은 A\!**  
**RefClassA 소멸자에서: 관리 되지 않는**  
**in RefClassA constructor: first**  
**Hello from first A\!**  
**in RefClassA destructor: first**  
**in RefClassA constructor: second**  
**Hello from second B\!**  
**Hello from second A\!**  
**Hello from second A\!**  
**in RefClassA destructor: second**  
**done**   
## 요구 사항  
 **Header file** \<msclr\\auto\_gcroot.h\>  
  
 **Namespace** msclr  
  
## 참고 항목  
 [auto\_gcroot 멤버](../dotnet/auto-gcroot-members.md)   
 [auto\_gcroot::attach](../dotnet/auto-gcroot-attach.md)   
 [auto\_gcroot::operator\=](../dotnet/auto-gcroot-operator-assign.md)   
 [auto\_gcroot::~auto\_gcroot](../dotnet/auto-gcroot-tilde-auto-gcroot.md)