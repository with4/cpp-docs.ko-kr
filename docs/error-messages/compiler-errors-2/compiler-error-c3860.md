---
title: "컴파일러 오류 C3860 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3860"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3860"
ms.assetid: 1fb5110d-594e-4f1c-8773-888233af1313
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C3860
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

클래스 템플릿 이름 뒤의 템플릿 인수 목록에는 템플릿 매개 변수 목록에 사용되는 순서와 같은 순서로 매개 변수를 나열해야 합니다.  
  
 제네릭 또는 템플릿 인수 목록의 형식이 올바르지 않습니다.  
  
 다음 샘플에서는 C3860 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3860.cpp  
// compile with: /LD  
template <class T1, class T2>  
struct A {  
   void f();  
};  
  
template <class T2, class T1>  
void A<T1, T2>::f() {}   // C3860  
```  
  
 다음과 같이 해결할 수 있습니다.  
  
```  
// C3860b.cpp  
// compile with: /c  
template <class T1, class T2>  
struct A {  
   void f();  
};  
  
template <class T2, class T1>  
void A<T2, T1>::f() {}  
```  
  
 제네릭을 사용하는 경우에도 C3860이 발생할 수 있습니다.  
  
```  
// C3860c.cpp  
// compile with: /clr  
generic<class T,class U>  
ref struct GC {  
   void f();  
};  
  
generic<class T, class U>  
void GC<T,T>::f() {}   // C3860  
```  
  
 다음과 같이 해결할 수 있습니다.  
  
```  
// C3860d.cpp  
// compile with: /clr /c  
generic<class T,class U>  
ref struct GC {  
   void f();  
};  
  
generic<class T, class U>  
void GC<T,U>::f() {}  
```