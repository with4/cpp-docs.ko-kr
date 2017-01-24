---
title: "참조 형식에 대한 C++ 스택 의미 체계 | Microsoft Docs"
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
  - "참조 형식, C++ 스택 의미 체계"
ms.assetid: 319a1304-f4a4-4079-8b84-01cec847d531
caps.latest.revision: 15
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 참조 형식에 대한 C++ 스택 의미 체계
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prior to Visual C\+\+ 2005, an instance of a reference type could only be created using the `new` operator, which created the object on the garbage collected heap.  However, you can now create an instance of a reference type using the same syntax that you would use to create an instance of a native type on the stack.  So, you do not need to use [ref new, gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md) to create an object of a reference type.  And when the object goes out of scope, the compiler calls the object's destructor.  
  
## 설명  
 When you create an instance of a reference type using stack semantics, the compiler does internally create the instance on the garbage collected heap \(using `gcnew`\).  
  
 When the signature or return type of a function includes an instance of a by\-value reference type, the function will be marked in the metadata as requiring special handling \(with modreq\).  This special handling is currently only provided by Visual C\+\+ clients; other languages do not currently support consuming functions or data that use reference types created with stack semantics.  
  
 One reason to use `gcnew` \(dynamic allocation\) instead of stack semantics would be if the type has no destructor.  Also, using reference types created with stack semantics in function signatures would not be possible if you want your functions to be consumed by languages other than Visual C\+\+.  
  
 The compiler will not generate a copy constructor for a reference type.  Therefore, if you define a function that uses a by\-value reference type in the signature, you must define a copy constructor for the reference type.  A copy constructor for a reference type has a signature of the following form: `R(R%){}`.  
  
 The compiler will not generate a default assignment operator for a reference type.  An assignment operator allows you to create an object using stack semantics and initialize it with an existing object created using stack semantics.  An assignment operator for a reference type has a signature of the following form: `void operator=( R% ){}`.  
  
 If your type's destructor releases critical resources and you use stack semantics for reference types, you do not need to explicitly call the destructor \(or call `delete`\).  For more information on destructors in reference types, see [Visual C\+\+의 소멸자 및 종료자](../misc/destructors-and-finalizers-in-visual-cpp.md).  
  
 A compiler\-generated assignment operator will follow the usual standard C\+\+ rules with the following additions:  
  
-   Any non\-static data members whose type is a handle to a reference type will be shallow copied \(treated like a non\-static data member whose type is a pointer\).  
  
-   Any non\-static data member whose type is a value type will be shallow copied.  
  
-   Any non\-static data member whose type is an instance of a reference type will invoke a call to the reference type’s copy constructor.  
  
 The compiler also provides a `%` unary operator to convert an instance of a reference type created using stack semantics to its underlying handle type.  
  
 The following reference types are not available for use with stack semantics:  
  
-   [delegate](../windows/delegate-cpp-component-extensions.md)  
  
-   [Arrays](../windows/arrays-cpp-component-extensions.md)  
  
-   <xref:System.String>  
  
## 예제  
  
### 설명  
 The following code sample shows how to declare instances of reference types with stack semantics, how the assignment operator and copy constructor works, and how to initialize a tracking reference with reference type created using stack semantics.  
  
### 코드  
  
```  
// stack_semantics_for_reference_types.cpp  
// compile with: /clr  
ref class R {  
public:  
   int i;  
   R(){}  
  
   // assignment operator  
   void operator=(R% r) {  
      i = r.i;  
   }  
  
   // copy constructor  
   R(R% r) : i(r.i) {}  
};  
  
void Test(R r) {}   // requires copy constructor  
  
int main() {  
   R r1;  
   r1.i = 98;  
  
   R r2(r1);   // requires copy constructor  
   System::Console::WriteLine(r1.i);  
   System::Console::WriteLine(r2.i);  
  
   // use % unary operator to convert instance using stack semantics  
   // to its underlying handle  
   R ^ r3 = %r1;  
   System::Console::WriteLine(r3->i);  
  
   Test(r1);  
  
   R r4;  
   R r5;  
   r5.i = 13;  
   r4 = r5;   // requires a user-defined assignment operator  
   System::Console::WriteLine(r4.i);  
  
   // initialize tracking reference  
   R % r6 = r4;  
   System::Console::WriteLine(r6.i);  
}  
```  
  
### Output  
  
```  
98  
98  
98  
13  
13  
```  
  
## 참고 항목  
 [Classes and Structs](../windows/classes-and-structs-cpp-component-extensions.md)