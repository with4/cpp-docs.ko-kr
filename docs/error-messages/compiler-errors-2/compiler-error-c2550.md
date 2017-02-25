---
title: "컴파일러 오류 C2550 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2550"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2550"
ms.assetid: 3293f53e-ee66-4035-920d-34e115c3a24c
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2550
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 생성자 이니셜라이저 목록은 생성자 정의에만 사용할 수 있습니다.  
  
 기본 클래스 이니셜라이저 목록은 생성자가 아닌 함수의 정의에만 사용됩니다.  
  
 다음 샘플에서는 C2550 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2550.cpp  
// compile with: /c  
class C {  
public:  
   C();  
};  
  
class D : public C {  
public:  
   D();  
   void func();  
};  
  
void D::func() : C() {}  // C2550  
D::D() : C() {}   // OK  
```