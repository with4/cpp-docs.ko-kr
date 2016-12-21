---
title: "컴파일러 오류 C2876 | Microsoft Docs"
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
  - "C2876"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2876"
ms.assetid: 8b674bf1-f9f4-4a8e-8127-e884c1d1708f
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2876
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class::symbol' : 모든 오버로드에 액세스할 수 있는 것은 아닙니다.  
  
 파생 클래스는 기본 클래스의 함수에 대한 모든 오버로드된 형식에 액세스할 수 있어야 합니다.  
  
 다음 샘플에서는 C2876 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2876.cpp  
// compile with: /c  
class A {  
public:     
   double a(double);  
private:  
   int a(int);  
};  
  
class B : public A {  
   using A::a;   // C2876 one overload is private in base class  
};  
```