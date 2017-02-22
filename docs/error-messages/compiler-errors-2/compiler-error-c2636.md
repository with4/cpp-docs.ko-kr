---
title: "컴파일러 오류 C2636 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2636"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2636"
ms.assetid: 379873ec-8d05-49f8-adf1-b067bc07bdb8
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2636
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 포인터는 참조 멤버를 가리킬 수 없습니다.  
  
 참조 멤버에 대한 포인터가 선언되었습니다.  
  
 다음 샘플에서는 C2636 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2636.cpp  
struct S {};  
int main() {  
   int &S::*prs;   // C2636  
   int S::*prs1;   // OK  
   int *S::*prs2;   // OK  
}  
```