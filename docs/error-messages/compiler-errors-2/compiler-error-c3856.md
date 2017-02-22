---
title: "컴파일러 오류 C3856 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3856"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3856"
ms.assetid: 242d9322-c325-4f20-be58-b2be6da56d60
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C3856
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type': 클래스가 클래스 형식이\(가\) 아닙니다.  
  
 이 오류가 발생하는 가장 일반적인 이유는 선언 시점보다 정의 시점에 더 많은 제네릭 또는 템플릿 매개 변수 목록이 있기 때문입니다.  
  
 다음 샘플에서는 C3856 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3856.cpp  
template <class T>   
struct S {  
   template <class T1>   
   struct S1;   
   void f();   
};  
  
template <class T>   // C3856  
template <class T1>  
template <class T2>  // extra template parameter list in definition  
struct S<T>::S1{};  
```  
  
 다음과 같이 해결할 수 있습니다.  
  
```  
// C3856b.cpp  
// compile with: /c  
template <class T>   
struct S {  
   template <class T1>   
   struct S1;   
   void f();   
};  
  
template <class T>  
template <class T1>  
struct S<T>::S1{};  
```  
  
 제네릭을 사용하는 경우에도 C3856이 발생할 수 있습니다.  
  
```  
// C3856c.cpp  
// compile with: /clr  
generic <class T>  
ref struct GS {  
   generic <class U>  
   ref struct GS2;  
};  
  
generic <class T>  
generic <class U>  
generic <class V>  
ref struct GS<T>::GS2 {};   // C3856  
```  
  
 다음과 같이 해결할 수 있습니다.  
  
```  
// C3856d.cpp  
// compile with: /clr /c  
generic <class T>  
ref struct GS {  
   generic <class U>  
   ref struct GS2;  
};  
  
generic <class T>  
generic <class U>  
ref struct GS<T>::GS2 {};  
```