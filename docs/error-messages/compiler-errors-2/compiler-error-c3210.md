---
title: "컴파일러 오류 C3210 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3210"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3210"
ms.assetid: c6e9d309-fabc-4e7d-b526-be20d9fe3f6a
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C3210
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type': 액세스 선언은 기본 클래스 멤버에만 적용할 수 있습니다.  
  
 [using 선언](../../cpp/using-declaration.md)을 잘못 지정했습니다.  
  
## 예제  
 다음 샘플에서는 C3210 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3210.cpp  
// compile with: /c  
struct A {  
protected:  
   int i;  
};  
  
struct B {  
   using A::i;   // C3210  
};  
  
struct C : public A {  
   using A::i;   // OK  
};  
```