---
title: "컴파일러 경고 (수준 4) C4239 | Microsoft Docs"
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
  - "C4239"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4239"
ms.assetid: a23dc16a-649e-4870-9a24-275de1584fcd
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 4) C4239
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

비표준 확장이 사용됨 : 'token' : 'type'에서 'type'\(으\)로의 변환입니다.  
  
 이러한 형식 변환은 C\+\+ 표준에서는 사용할 수 없지만 여기서는 확장으로 사용할 수 있습니다.  이 경고에는 항상 위반된 언어 규칙 설명이 적어도 한 줄 이상 함께 표시됩니다.  
  
## 예제  
 다음 샘플에서는 C4239 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4239.cpp  
// compile with: /W4 /c  
struct C {  
   C() {}  
};  
  
void func(void) {  
   C & rC = C();   // C4239  
   const C & rC2 = C();   // OK  
   rC2;  
}  
```  
  
## 예제  
 정수 계열 형식에서 열거형으로의 변환은 허용되지 않습니다.  
  
 다음 샘플에서는 C4239 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4239b.cpp  
// compile with: /W4 /c  
enum E { value };   
struct S {   
   E e : 2;   
} s = { 5 };   // C4239   
// try the following line instead  
// } s = { (E)5 };  
```