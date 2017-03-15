---
title: "컴파일러 경고 (수준 3) C4281 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4281"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4281"
ms.assetid: a9771261-5725-4fc6-87b6-16cf92113a25
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 경고 (수준 3) C4281
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' 형식에서 'operator –\>' 재귀가 발생했습니다.  
  
 코드에 자신을 호출하는 **operator–\>\>**를 사용했습니다.  
  
 다음 샘플에서는 C4281 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4281.cpp  
// compile with: /W3 /WX  
struct A;  
struct B;  
struct C;  
  
struct A  
{  
   int z;  
   B& operator->();  
};  
  
struct B  
{  
   C& operator->();  
};  
  
struct C  
{  
   A& operator->();  
};  
  
void f(A p)  
{  
   int i = p->z; // C4281  
}  
```