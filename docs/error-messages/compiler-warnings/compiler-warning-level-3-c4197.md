---
title: "컴파일러 경고 (수준 3) C4197 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4197"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4197"
ms.assetid: f766feef-82b0-4d81-8a65-33628c7db196
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 3) C4197
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : 캐스트의 최상위 volatile은 무시됩니다.  
  
 컴파일러가 [volatile](../../cpp/volatile-cpp.md)로 한정된 r\-value 형식으로의 캐스트 또는 r\-value 형식에서 volatile로 한정된 일부 형식으로의 캐스트를 검색했습니다.  C 표준\(6.5.3\)에 따라, 한정된 형식과 관련된 속성은 l\-value 식에만 의미 있습니다.  
  
 다음 샘플에서는 C4197 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4197.cpp  
// compile with: /W3  
#include <stdio.h>  
#include <signal.h>  
#include <stdlib.h>  
  
void sigproc(int);  
struct S  
{  
   int i;  
} s;  
  
int main()  
{  
   signal(SIGINT, sigproc);  
   s.i = 1;  
   S *pS = &s;  
   for ( ; (volatile int)pS->i ; )   // C4197  
      break;  
   // for ( ; *(volatile int *)&pS->i ; )   // OK  
   //    break;  
}  
  
void sigproc(int) // ctrl-C  
{  
   signal(SIGINT, sigproc);  
   s.i = 0;  
}  
  
```