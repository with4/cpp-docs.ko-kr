---
title: "컴파일러 오류 C2250 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2250"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2250"
ms.assetid: f990986f-5c7d-4af4-a25c-b35540f1e217
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2250
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 'class::member'의 상속이 모호합니다.  
  
 파생 클래스가 가상 기본 클래스의 가상 함수 재정의를 둘 이상 상속합니다.  파생 클래스에서 이러한 재정의는 모호합니다.  
  
 다음 샘플에서는 C2286 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2250.cpp  
// compile with: /c  
// C2250 expected  
struct V {  
   virtual void vf();  
};  
  
struct A : virtual V {  
   void vf();  
};  
  
struct B : virtual V {  
   void vf();  
};  
  
struct D : A, B {  
   // Uncomment the following line to resolve.  
   // void vf();  
};  
```