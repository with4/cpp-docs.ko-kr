---
title: "컴파일러 오류 C2450 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2450"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2450"
ms.assetid: 929f1c06-8774-468b-be2a-f428757875a2
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2450
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' 형식의 switch 식은 올바르지 않습니다.  
  
 `switch` 식이 잘못된 형식으로 계산됩니다.  정수 형식으로의 명확한 변환을 통해 정수 형식이나 클래스 형식으로 계산되어야 합니다.  사용자 정의 형식으로 계산되는 경우에는 변환 연산자를 제공해야 합니다.  
  
 다음 샘플에서는 C2450 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2450.cpp  
class X {  
public:  
   int i;  
} x;  
  
class Y {  
public:  
   int i;  
   operator int() { return i; }   // conversion operator  
} y;  
  
int main() {  
   int j = 1;  
   switch ( x ) {   // C2450, x is not type int  
   // try the following line instead  
   // switch ( y ) {  
      default:  ;  
   }  
}  
```