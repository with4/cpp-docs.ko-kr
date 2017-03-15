---
title: "컴파일러 오류 C2051 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2051"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2051"
ms.assetid: 81c0469a-78e2-49fa-bd76-97cdb135e3ea
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C2051
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

case 식이 상수가 아닙니다.  
  
 Case 식은 정수 계열 상수여야 합니다.  
  
 다음 샘플에서는 C2051 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2051.cpp  
class X {};  
  
int main() {  
   static X x;  
   int i = 0;  
  
   switch (i) {  
      case x:   // C2051 use constant expression to resolve error  
         break;  
      default:  
         break;  
   }  
}  
```  
  
 다음과 같이 해결할 수 있습니다.  
  
```  
// C2051b.cpp  
class X {};  
  
int main() {  
   static X x;  
   int i = 0;  
  
   switch (i) {  
      case 1:  
         break;  
      default:  
         break;  
   }  
}  
```