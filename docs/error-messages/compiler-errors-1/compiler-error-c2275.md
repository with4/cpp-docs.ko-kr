---
title: "컴파일러 오류 C2275 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2275"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2275"
ms.assetid: c1eafa71-48de-46e0-82f3-b575538ef205
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C2275
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 이 형식을 식으로 잘못 사용했습니다.  
  
 식에서 `->` 연산자가 `typedef` 식별자와 함께 사용됩니다.  
  
 다음 샘플에서는 C2275 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2275.cpp  
typedef struct S {  
    int mem;  
} *S_t;  
void func1( int *parm );  
void func2() {  
    func1( &S_t->mem );   // C2275, S_t is a typedef  
}  
```