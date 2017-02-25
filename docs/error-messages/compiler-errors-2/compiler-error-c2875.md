---
title: "컴파일러 오류 C2875 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2875"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2875"
ms.assetid: d589fc0c-08b2-4a79-bc0e-dca5eb80bdd5
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2875
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

using 선언 때문에 'class::identifier'이\(가\) 여러 번 선언됩니다.  
  
 이 선언은 동일 항목을 두 번 정의합니다.  
  
 다음 샘플에서는 C2875 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2875.cpp  
struct A {  
   void f(int*);  
};  
  
struct B {  
   void f(double*);  
};  
  
struct AB : A, B {  
   using A::f;  
   using A::f;   // C2875  
   using B::f;  
};  
```