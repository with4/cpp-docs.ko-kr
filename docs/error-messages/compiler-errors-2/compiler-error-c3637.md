---
title: "컴파일러 오류 C3637 | Microsoft Docs"
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
  - "C3637"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3637"
ms.assetid: 72391377-8519-43d9-870a-73a6423deb74
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3637
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function': friend 함수 정의는 함수 type의 특수화일 수 없습니다.  
  
 friend 함수가 템플릿이나 제네릭에 대해 잘못 정의되었습니다.  
  
 다음 샘플에서는 C3637 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3637.cpp  
template <class T>  
void f();  
  
struct S {  
   friend void f<int>() {}   // C3637  
};  
```  
  
 다음과 같이 해결할 수 있습니다.  
  
```  
// C3637b.cpp  
// compile with: /c  
template <class T>  
void f();  
  
struct S {  
   friend void f() {}  
};  
```  
  
 제네릭을 사용하는 경우에도 C3637이 발생할 수 있습니다.  
  
```  
// C3637c.cpp  
// compile with: /clr  
  
generic <class T>  
void gf();  
  
struct S {  
   friend void gf<int>() {}   // C3637  
};  
```  
  
 다음과 같이 해결할 수 있습니다.  
  
```  
// C3637d.cpp  
// compile with: /clr /c  
generic <class T>  
void gf();  
  
struct S {  
   friend void gf() {}  
};  
```