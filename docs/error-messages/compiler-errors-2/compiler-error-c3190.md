---
title: 컴파일러 오류 C3190 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3190
dev_langs:
- C++
helpviewer_keywords:
- C3190
ms.assetid: 7c701afa-85a7-4f7a-8881-0662436ac244
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 797d7299c73574db28dd5c09284602e167485204
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33248528"
---
# <a name="compiler-error-c3190"></a>컴파일러 오류 C3190
제공 된 템플릿 인수를 갖는 ' 인스턴스화' t y'의 모든 멤버 함수의 명시적 인스턴스화가 아닙니다.  
  
 컴파일러는 명시적 함수 인스턴스화; 확인 시도를 검색 했습니다. 그러나 제공 된 형식 인수는 가능한 기능의 일치 하지 않습니다.  
  
 다음 샘플에서는 C3190 오류가 생성 됩니다.  
  
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