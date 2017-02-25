---
title: "컴파일러 오류 C3379 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3379"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3379"
ms.assetid: a66c2c4e-091c-4426-9cde-7c4cfb2ffce1
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# 컴파일러 오류 C3379
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class' : 중첩 클래스 선언의 일부로 어셈블리 액세스 지정자를 사용할 수 없습니다.  
  
 [public](../../cpp/public-cpp.md) 및 [private](../../cpp/private-cpp.md) 키워드는 관리되는 형식\(예: 클래스 또는 구조체\)에 적용될 때 클래스가 어셈블리 메타데이터를 통해 노출되는지 여부를 나타냅니다.  `public` 또는 `private`는 중첩 클래스에 적용될 수 없으며, 중첩 클래스는 바깥쪽 클래스의 어셈블리 액세스 권한을 상속합니다.  
  
 `ref` 및 `value` 키워드가 [\/clr](../../build/reference/clr-common-language-runtime-compilation.md)와 함께 사용되는 경우에는 클래스가 관리되는 클래스임을 나타냅니다\([Classes and Structs](../../windows/classes-and-structs-cpp-component-extensions.md) 참조\).  
  
 다음 샘플에서는 C3379 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3379a.cpp  
// compile with: /clr  
using namespace System;  
  
public ref class A {  
public:  
   static int i = 9;  
  
   public ref class BA {   // C3379  
   // try the following line instead  
   // ref class BA {  
   public:  
      static int ii = 8;  
   };  
};  
  
int main() {  
  
   A^ myA = gcnew A;  
   Console::WriteLine(myA->i);  
  
   A::BA^ myBA = gcnew A::BA;  
   Console::WriteLine(myBA->ii);  
}  
```  
  
 다음 샘플에서는 C3379 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3379b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
  
public __gc class A {  
public:  
   static int i = 9;  
  
   public __gc class BA {   // C3379  
   // try the following line instead  
   // __gc class BA {  
   public:  
      static int ii = 8;  
   };  
};  
  
int main() {  
  
   A *myA = new A;  
   Console::WriteLine(myA->i);  
  
   A::BA *myBA = new A::BA;  
   Console::WriteLine(myBA->ii);  
}  
```