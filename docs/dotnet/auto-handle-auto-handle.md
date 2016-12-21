---
title: "auto_handle::auto_handle | Microsoft Docs"
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
  - "auto_handle::auto_handle"
  - "msclr.auto_handle.auto_handle"
  - "auto_handle.auto_handle"
  - "msclr::auto_handle::auto_handle"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "auto_handle 메서드"
ms.assetid: 0b68ab31-023c-4224-9601-9231412c4e13
caps.latest.revision: 10
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# auto_handle::auto_handle
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`auto_handle` 생성자  
  
## 구문  
  
```  
auto_handle();  
auto_handle(  
   _element_type ^ _ptr  
);  
auto_handle(  
   auto_handle<_element_type> % _right  
);  
template<typename _other_type>  
auto_handle(  
   auto_handle<_other_type> % _right  
);  
```  
  
#### 매개 변수  
 `_ptr`  
 소유 개체입니다.  
  
 `_right`  
 기존 `auto_handle`입니다.  
  
## 예제  
  
```  
// msl_auto_handle_auto_handle.cpp  
// compile with: /clr  
#include "msclr\auto_handle.h"  
  
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
  
int main()  
{  
   {  
      auto_handle<RefClassA> a(gcnew RefClassA( "first" ) );  
      a->PrintHello();  
   }  
  
   {  
      auto_handle<RefClassB> b(gcnew RefClassB( "second" ) );  
      b->PrintHello();  
      auto_handle<RefClassA> a(b); //construct from derived type  
      a->PrintHello();  
      auto_handle<RefClassA> a2(a); //construct from same type  
      a2->PrintHello();  
   }  
  
   Console::WriteLine("done");  
}  
```  
  
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
 **Header file** \<msclr\\auto\_handle.h\>  
  
 **Namespace** msclr  
  
## 참고 항목  
 [auto\_handle 멤버](../dotnet/auto-handle-members.md)   
 [auto\_handle::operator\=](../dotnet/auto-handle-operator-assign.md)   
 [auto\_handle::~auto\_handle](../dotnet/auto-handle-tilde-auto-handle.md)