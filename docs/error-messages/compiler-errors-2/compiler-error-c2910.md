---
title: "컴파일러 오류 C2910 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2910"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2910"
ms.assetid: 09c50e6a-e099-42f6-8ed6-d80e292a7a36
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2910
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 명시적으로 특수화할 수 없습니다.  
  
 함수를 명시적으로 두 번 특수화하려고 했습니다.  
  
 다음 샘플에서는 C2910 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2910.cpp  
// compile with: /c  
template <class T>  
struct S;  
  
template <> struct S<int> { void f() {} };  
template <> void S<int>::f() {}   // C2910 delete this specialization  
```  
  
 비템플릿 멤버를 명시적으로 특수화하려고 할 경우에도 C2910 오류가 발생할 수 있습니다.  즉, 함수 템플릿만 명시적으로 특수화할 수 있습니다.  
  
 다음 샘플에서는 C2910 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2910b.cpp  
// compile with: /c  
template <class T> struct A {  
   A(T* p);  
};  
  
template <> struct A<void> {  
   A(void* p);  
};  
  
template <class T>  
inline A<T>::A(T* p) {}  
  
template <> A<void>::A(void* p){}   // C2910  
// try the following line instead  
// A<void>::A(void* p){}  
```  
  
 이 오류는 또한 Visual Studio .NET 2003에서 컴파일러 규칙에 따른 작업을 수행한 결과로 발생할 수 있습니다.  
  
 Visual Studio .NET 2003과 Visual Studio .NET 버전의 Visual C\+\+ 모두에서 올바른 코드가 되도록 하려면 `template <>`를 제거하십시오.  
  
 다음 샘플에서는 C2910 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2910c.cpp  
// compile with: /c  
template <class T> class A {  
   void f();  
};  
  
template <> class A<int> {  
   void f();  
};  
  
template <> void A<int>::f() {}   // C2910  
// try the following line instead  
// void A<int>::f(){}   // OK  
```