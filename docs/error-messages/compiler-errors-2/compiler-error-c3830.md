---
title: "컴파일러 오류 C3830 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3830"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3830"
ms.assetid: c9798f88-5001-4067-9fb1-09957ddc6fa8
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3830
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type1': 'type2'에서 상속할 수 없습니다. 값 형식은 인터페이스 클래스에서만 상속할 수 있습니다.  
  
 값 형식은 기본 클래스를 상속할 수 없습니다.  자세한 내용은 [Classes and Structs](../../windows/classes-and-structs-cpp-component-extensions.md)을 참조하십시오.  
  
 다음 샘플에서는 C3830 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3830a.cpp  
// compile with: /clr /c  
public value struct MyStruct4 {  
   int i;  
};  
  
public value class MyClass : public MyStruct4 {};   // C3830  
  
// OK  
public interface struct MyInterface4 {  
   void i();  
};  
  
public value class MyClass2 : public MyInterface4 {  
public:  
   virtual void i(){}  
};  
```  
  
 **Managed Extensions for C\+\+**  
  
 `__value` 형식은 기본 클래스를 상속할 수 없습니다.  
  
 다음 샘플에서는 C3830 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3830b.cpp  
// compile with: /clr:oldSyntax /c  
#using <mscorlib.dll>  
__value struct v : public System::Object {};   // C3830  
__value struct w {};   // OK  
```