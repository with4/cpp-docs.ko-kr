---
title: "pop_macro | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-pragma.pop_macro"
  - "pop_macro_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "pop_macro pragma"
  - "pragma, pop_macro"
ms.assetid: 3b5489d0-69ba-4c66-b572-2748af0f12bb
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# pop_macro
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

*macro\_name* 매크로 값을 이 매크로의 스택 맨 위에 있는 값으로 설정합니다.  
  
## 구문  
  
```  
  
#pragma pop_macro("  
macro_name  
")  
  
```  
  
## 설명  
 **pop\_macro**를 수행하기 전에 *macro\_name*에 대한 [push\_macro](../preprocessor/push-macro.md)를 먼저 실행해야 합니다.  
  
## 예제  
  
```  
// pragma_directives_pop_macro.cpp  
// compile with: /W1  
#include <stdio.h>  
#define X 1  
#define Y 2  
  
int main() {  
   printf("%d",X);  
   printf("\n%d",Y);  
   #define Y 3   // C4005  
   #pragma push_macro("Y")  
   #pragma push_macro("X")  
   printf("\n%d",X);  
   #define X 2   // C4005  
   printf("\n%d",X);  
   #pragma pop_macro("X")  
   printf("\n%d",X);  
   #pragma pop_macro("Y")  
   printf("\n%d",Y);  
}  
```  
  
  **1**  
**2**  
**1**  
**2**  
**1**  
**3**   
## 참고 항목  
 [Pragma 지시문 및 \_\_Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)