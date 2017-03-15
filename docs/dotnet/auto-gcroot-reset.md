---
title: "auto_gcroot::reset | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "msclr::auto_gcroot::reset"
  - "auto_gcroot::reset"
  - "msclr.auto_gcroot.reset"
  - "auto_gcroot.reset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "reset 메서드"
ms.assetid: dd58467f-3885-4a15-99fb-ed6dd5d19622
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# auto_gcroot::reset
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Destroy the current owned object and optionally take possession of a new object.  
  
## 구문  
  
```  
void reset(  
   _element_type _new_ptr = nullptr  
);  
```  
  
#### 매개 변수  
 `_new_ptr`  
 \(Optional\) The new object.  
  
## 예제  
  
```  
// msl_auto_gcroot_reset.cpp  
// compile with: /clr  
#include <msclr\auto_gcroot.h>  
  
using namespace System;  
using namespace msclr;  
  
ref class ClassA {  
   String^ m_s;  
public:  
   ClassA( String^ s ) : m_s( s ) {  
      Console::WriteLine( "ClassA constructor: " + m_s );  
   }  
   ~ClassA() {  
      Console::WriteLine( "ClassA destructor: " + m_s );  
   }  
  
   void PrintHello() {  
      Console::WriteLine( "Hello from {0} A!", m_s );  
   }  
};  
  
int main()  
{  
   auto_gcroot<ClassA^> agc1 = gcnew ClassA( "first" );  
   agc1->PrintHello();  
  
   ClassA^ ha = gcnew ClassA( "second" );  
   agc1.reset( ha ); // release first object, reference second  
   agc1->PrintHello();  
  
   agc1.reset(); // release second object, set to nullptr  
  
   Console::WriteLine( "done" );  
}  
```  
  
  **ClassA constructor: first**  
**Hello from first A\!**  
**ClassA constructor: second**  
**ClassA destructor: first**  
**Hello from second A\!**  
**ClassA destructor: second**  
**done**   
## 요구 사항  
 **Header file** \<msclr\\auto\_gcroot.h\>  
  
 **Namespace** msclr  
  
## 참고 항목  
 [auto\_gcroot 멤버](../dotnet/auto-gcroot-members.md)   
 [auto\_gcroot::release](../dotnet/auto-gcroot-release.md)   
 [auto\_gcroot::attach](../dotnet/auto-gcroot-attach.md)