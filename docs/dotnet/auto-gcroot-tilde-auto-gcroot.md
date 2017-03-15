---
title: "auto_gcroot::~auto_gcroot | Microsoft Docs"
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
  - "auto_gcroot::~auto_gcroot"
  - "~auto_gcroot"
  - "auto_gcroot.~auto_gcroot"
  - "msclr::auto_gcroot::~auto_gcroot"
  - "msclr.auto_gcroot.~auto_gcroot"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "auto_gcroot::~auto_gcroot"
ms.assetid: 3c970d43-0cb1-4b27-8bee-0394d91b4739
caps.latest.revision: 11
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# auto_gcroot::~auto_gcroot
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The `auto_gcroot` destructor.  
  
## 구문  
  
```  
~auto_gcroot();  
```  
  
## 설명  
 The destructor also destructs the owned object.  
  
## 예제  
  
```  
// msl_auto_gcroot_dtor.cpp  
// compile with: /clr  
#include <msclr\auto_gcroot.h>  
  
using namespace System;  
using namespace msclr;  
  
ref class ClassA {  
public:  
   ClassA() { Console::WriteLine( "ClassA constructor" ); }  
   ~ClassA() { Console::WriteLine( "ClassA destructor" ); }  
};  
  
int main()  
{  
   // create a new scope for a:  
   {  
      auto_gcroot<ClassA^> a = gcnew ClassA;  
   }  
   // a goes out of scope here, invoking its destructor  
   // which in turns destructs the ClassA object.  
  
   Console::WriteLine( "done" );  
}  
```  
  
  **ClassA constructor**  
**ClassA destructor**  
**done**   
## 요구 사항  
 **Header file** \<msclr\\auto\_gcroot.h\>  
  
 **Namespace** msclr  
  
## 참고 항목  
 [auto\_gcroot 멤버](../dotnet/auto-gcroot-members.md)   
 [auto\_gcroot::release](../dotnet/auto-gcroot-release.md)   
 [auto\_gcroot::auto\_gcroot](../dotnet/auto-gcroot-auto-gcroot.md)