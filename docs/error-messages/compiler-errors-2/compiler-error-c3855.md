---
title: "컴파일러 오류 C3855 | Microsoft Docs"
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
  - "C3855"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3855"
ms.assetid: ed90f8c0-4154-4243-b066-493913df5727
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3855
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class': 형식 매개 변수 'param'이\(가\) 선언과 호환되지 않습니다.  
  
 컴파일러에서 서로 다른 이름을 사용하는 형식 없는 템플릿 또는 제네릭 매개 변수를 발견했습니다.  이 오류는 템플릿 특수화의 정의에 지정된 템플릿 매개 변수가 해당 선언과 호환되지 않을 때 발생합니다.  
  
 다음 샘플에서는 C3855 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3855.cpp  
template <int N>  
struct C {  
   void f();  
};  
  
template <char N>  
void C<N>::f() {}   // C3855  
```  
  
 다음과 같이 해결할 수 있습니다.  
  
```  
// C3855b.cpp  
// compile with: /c  
template <int N>  
struct C {  
   void f();  
};  
  
template <int N>  
void C<N>::f() {}  
```  
  
 제네릭을 사용하는 경우에도 C3855가 발생할 수 있습니다.  
  
```  
// C3855c.cpp  
// compile with: /clr  
generic <class T>  
ref struct GC1 {  
   generic <class U>  
   ref struct GC2;  
};  
  
generic <class T>  
generic <class U>  
generic <class V>  
ref struct GC1<T>::GC2 { };   // C3855  
```  
  
 다음과 같이 해결할 수 있습니다.  
  
```  
// C3855d.cpp  
// compile with: /clr /c  
generic <class T>  
ref struct GC1 {  
   generic <class U>  
   ref struct GC2;  
};  
  
generic <class T>  
generic <class U>  
ref struct GC1<T>::GC2 { };  
```