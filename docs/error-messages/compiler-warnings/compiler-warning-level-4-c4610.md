---
title: "컴파일러 경고 (수준 4) C4610 | Microsoft Docs"
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
  - "C4610"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4610"
ms.assetid: 23c1a16c-9ca9-4bf6-9911-a72b785560c2
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 4) C4610
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

개체 'class'을\(를\) 인스턴스화할 수 없습니다. 사용자 정의 생성자가 있어야 합니다.  
  
 클래스에 사용자 정의 생성자나 기본 생성자가 없으므로  인스턴스화가 수행되지 않습니다.  다음 샘플에서는 C4610 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4610.cpp  
// compile with: /W4  
struct A {  
   int &j;  
  
   A& A::operator=( const A& );  
};   // C4610  
  
/* use this structure definition to resolve the warning  
struct B {  
   int &k;  
  
   B(int i = 0) : k(i) {  
   }  
  
   B& B::operator=( const B& );  
} b;  
*/  
  
int main() {  
}  
```