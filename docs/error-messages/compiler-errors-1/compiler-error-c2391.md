---
title: "컴파일러 오류 C2391 | Microsoft Docs"
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
  - "C2391"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2391"
ms.assetid: 63a9c6b9-03cc-4517-885c-bdcd048643b3
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2391
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 형식을 정의하는 동안에는 'friend'를 사용할 수 없습니다.  
  
 `friend` 선언에는 완전한 클래스 선언이 포함됩니다.  `friend` 선언은 멤버 함수나 정교한 형식 지정자를 지정할 수 있지만 완전한 클래스 선언은 지정할 수 없습니다.  
  
 다음 샘플에서는 C2326 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2391.cpp  
// compile with: /c  
class D {   
   void func( int );   
};  
  
class A {  
   friend class B { int i; };   // C2391  
  
   // OK  
   friend class C;  
   friend void D::func(int);  
};  
```