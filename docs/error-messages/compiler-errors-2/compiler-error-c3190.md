---
title: "컴파일러 오류 C3190 | Microsoft Docs"
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
  - "C3190"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3190"
ms.assetid: 7c701afa-85a7-4f7a-8881-0662436ac244
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3190
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

제공된 템플릿 인수를 사용하여 인스턴스화한 'instantiation'은\(는\) 'type' 멤버 함수의 명시적 인스턴스화가 아닙니다.  
  
 함수를 명시적으로 인스턴스화하려고 했습니다. 하지만 제공된 형식 인수가 사용할 수 있는 함수와 일치하지 않습니다.  
  
 다음 샘플에서는 C3190 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3190.cpp  
// compile with: /LD  
template<class T>  
struct A {  
   A(int x = 0) {  
   }  
   A(int x, int y) {  
   }  
};  
  
template A<float>::A();   // C3190  
// try the following line instead  
// template A<int>::A(int);  
  
struct Y {  
   template<class T> void f(T);  
};  
  
template<class T> void Y::f(T) { }  
  
template void Y::f(int,int);   // C3190  
  
template<class OT> class X {  
   template<class T> void f2(T,OT);  
};  
  
template<class OT> template<class T> void X<OT>::f2(T,OT) {}  
  
template void X<float>::f2<int>(int,char);   // C3190  
// try one of the following lines instead  
// template void X<char>::f2(int, char);  
// template void X<char>::f2<int>(int,char);  
// template void X<char>::f2<>(int,char);  
```