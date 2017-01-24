---
title: "컴파일러 오류 C2835 | Microsoft Docs"
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
  - "C2835"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2835"
ms.assetid: 41c70630-983f-4da2-8342-513cf48b0519
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2835
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

사용자 정의 변환 'type'에는 형식 매개 변수를 사용하지 않습니다.  
  
 사용자 정의 형식 변환에는 형식 매개 변수를 사용할 수 없습니다.  
  
 다음 샘플에서는 C2835 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2835.cpp  
class A {  
public:  
   char v_char;  
  
   A() {   
      v_char = 'A';   
   };  
   operator char(char a) {   // C2835  
   // try the following line instead  
   // operator char() {     
      return v_char + 1;   
   };  
};  
  
int main() {  
   A a;  
}  
```