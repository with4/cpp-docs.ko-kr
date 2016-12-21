---
title: "컴파일러 오류 C2105 | Microsoft Docs"
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
  - "C2105"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2105"
ms.assetid: 19b7f7bc-a9da-4d23-8193-005b6d09274f
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2105
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator'에 l\-value가 필요합니다.  
  
 연산자에는 l\-value가 피연산자로 포함되어야 합니다.  
  
 다음 샘플에서는 C2105 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2105.cpp  
int main() {  
   unsigned char * p1 = 0;  
   unsigned int * p2 = (unsigned int *)p1;  
   p2++;  
  
   unsigned int * p = 0;  
   p++;   // ok  
  
   p2 = (unsigned int *)p1;  
   ((unsigned int *)p1)++;   // C2105  
}  
```  
  
 다음 샘플에서는 C2105 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2105b.cpp  
int main() {  
   int a[10] = {0};  
   int b[10] = {0};  
   ++(a , b);   // C2105  
  
   // OK  
   ++(a[0] , b[0]);  
   ++a[0];  
}  
```