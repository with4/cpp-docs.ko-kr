---
title: "컴파일러 오류 C2052 | Microsoft Docs"
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
  - "C2052"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2052"
ms.assetid: 922ca43b-b64b-4ef7-9611-c7313be3fd79
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2052
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : case 식의 형식이 잘못되었습니다.  
  
 Case 식은 정수 계열 상수여야 합니다.  
  
 다음 샘플에서는 C2052 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2052.cpp  
int main() {  
   int index = 0;  
   switch (index) {  
      case 1:  
         return 24;  
      case 1.0:   // C2052  
      // try the following line instead  
      // case 2:  
         return 23;  
   }  
}  
```