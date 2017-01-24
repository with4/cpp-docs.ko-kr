---
title: "방법: 인터페이스 정적 생성자 정의(C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "생성자[C++]"
  - "인터페이스 정적 생성자"
  - "정적 생성자, interface"
ms.assetid: 1f031cb2-e94f-43dc-819b-44cf2faaaa49
caps.latest.revision: 10
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 인터페이스 정적 생성자 정의(C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

An interface can have a static constructor, which can be used to initialize static data members.  A static constructor will be called at most once, and will be called before the first time a static interface member is accessed.  
  
 For more information on static constructors, see [방법: 클래스 또는 구조체에 정적 생성자 정의](../misc/how-to-define-static-constructors-in-a-class-or-struct.md).  
  
## 예제  
  
```  
// mcppv2_interface_class2.cpp  
// compile with: /clr  
using namespace System;  
  
interface struct MyInterface {  
   static int i;  
   static void Test() {  
      Console::WriteLine(i);  
   }  
  
   static MyInterface() {   
      Console::WriteLine("in MyInterface static constructor");  
      i = 99;  
   }  
};  
  
ref class MyClass : public MyInterface {};  
  
int main() {  
   MyInterface::Test();  
   MyClass::MyInterface::Test();  
  
   MyInterface ^ mi = gcnew MyClass;  
   mi->Test();  
}  
```  
  
  **in MyInterface static constructor**  
**99**  
**99**  
**99**   
## 참고 항목  
 [interface class](../windows/interface-class-cpp-component-extensions.md)