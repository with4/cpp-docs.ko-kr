---
title: "컴파일러 오류 C2804 | Microsoft Docs"
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
  - "C2804"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2804"
ms.assetid: b066e563-cca4-450c-8ba7-3b0d7a89f3ea
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2804
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이항 'operator operator'에 매개 변수가 너무 많습니다.  
  
 오버로드된 이항 연산자 멤버 함수는 둘 이상의 매개 변수를 사용하여 선언됩니다.  형식이 연산자의 바깥쪽 형식인 이항 연산자 멤버 함수의 첫 번째 피연산자 매개 변수가 적용됩니다.  
  
## 예제  
 다음 샘플에서는 C2804 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.  
  
```  
// C2804.cpp  
// compile by using: cl /c /W4 C2804.cpp  
class X {  
public:  
   X& operator+= (const X &left, const X &right);   // C2804  
   X& operator+= (const X &right);   // OK - left operand implicitly *this  
};  
  
int main() {  
   X x, y;  
   x += y;   // equivalent to x.operator+=(y)  
}  
```  
  
## 예제  
 다음 샘플에서는 C2804 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.  
  
```  
// C2804_2.cpp  
// compile with: /clr /c  
ref struct Y {  
   Y^ operator +(Y^ hY, int i);   // C2804  
   static Y^ operator +(Y^ hY, int i);   // OK  
   Y^ operator +(int i);   // OK  
};  
```