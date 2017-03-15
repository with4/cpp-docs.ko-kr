---
title: "컴파일러 오류 C2683 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2683"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2683"
ms.assetid: db605e4f-601b-4d05-92a1-c43ca24de08d
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# 컴파일러 오류 C2683
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'cast' : 'type'은\(는\) 다형 형식이 아닙니다.  
  
 [dynamic\_cast](../../cpp/dynamic-cast-operator.md)를 사용하여 비다형 클래스\(가상 함수가 없는 클래스\)에서 변환할 수 없습니다.  
  
 [static\_cast](../../cpp/static-cast-operator.md)를 사용하여 비다형 형식의 변환을 수행할 수 있습니다.  하지만 `static_cast`는 런타임 검사를 수행하지 않습니다.  
  
 다음 샘플에서는 C2683 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2683.cpp  
// compile with: /c  
class B { };  
class D : public B { };  
  
void f(B* pb) {  
   D* pd1 = dynamic_cast<D*>(pb);  // C2683  
   D* pd1 = static_cast<D*>(pb);   // OK  
}  
```