---
title: "auto_gcroot::get | Microsoft Docs"
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
  - "msclr::auto_gcroot::get"
  - "msclr.auto_gcroot.get"
  - "auto_gcroot::get"
  - "auto_gcroot.get"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "auto_gcroot::get"
ms.assetid: 0e922019-1cf5-4220-b5ab-6c4a2a6b40ec
caps.latest.revision: 13
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# auto_gcroot::get
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

포함된 개체를 가져옵니다.  
  
## 구문  
  
```  
_element_type get() const;  
```  
  
## 반환 값  
 포함된 개체입니다.  
  
## 예제  
  
```  
// msl_auto_gcroot_get.cpp  
// compile with: /clr  
#include <msclr\auto_gcroot.h>  
  
using namespace System;  
using namespace msclr;  
  
ref class ClassA {  
   String^ m_s;  
public:  
   ClassA( String^ s ) : m_s( s ){  
      Console::WriteLine( "in ClassA constructor:" + m_s );  
   }  
   ~ClassA() {  
      Console::WriteLine( "in ClassA destructor:" + m_s );  
   }  
  
   void PrintHello() {  
      Console::WriteLine( "Hello from {0} A!", m_s );  
   }  
};  
  
void PrintA( ClassA^ a ) {  
   a->PrintHello();  
}  
  
int main() {  
   auto_gcroot<ClassA^> a = gcnew ClassA( "first" );  
   a->PrintHello();  
  
   ClassA^ a2 = a.get();  
   a2->PrintHello();  
  
   PrintA( a.get() );  
}  
```  
  
  **in ClassA constructor:first**  
**Hello from first A\!**  
**Hello from first A\!**  
**Hello from first A\!**  
**in ClassA destructor:first**   
## 요구 사항  
 **Header file** \<msclr\\auto\_gcroot.h\>  
  
 **Namespace** msclr  
  
## 참고 항목  
 [auto\_gcroot 멤버](../dotnet/auto-gcroot-members.md)