---
title: "컴파일러 오류 C3240 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3240"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3240"
ms.assetid: 1a8dc213-b80c-47ae-ada0-e9554b635d1e
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 오류 C3240
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 'type'의 오버로드되지 않은 추상 멤버 함수여야 합니다.  
  
 정의된 함수가 기본 형식에 포함되어 있습니다.  함수는 가상 함수여야 합니다.  
  
## 예제  
 다음 샘플에서는 C3240 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3240.cpp  
// compile with: /c  
__interface I {  
   void f();  
};  
  
struct A1 : I {   
   void f() {}  
};  
  
struct A2 : I {   
   void f() = 0;  
};  
  
template <class T>   
struct A3 : T {  
   void T::f() {}  
};  
  
template <class T>   
struct A4 : T {  
   void T::f() {}  
};  
  
A3<A1> x;   // C3240  
A3<I> x2;  
A4<A2> x3;  
```