---
title: "컴파일러 오류 C2540 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2540"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2540"
ms.assetid: 92c805a3-2dd9-46ca-a63d-3845c18ecc95
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2540
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

배열 범위가 상수 식이 아닙니다.  
  
 배열은 상수 범위를 사용해야 합니다.  
  
 다음 샘플에서는 C2540 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2540.cpp  
void func(int n, int pC[]) {  
   int i = ((int [n])pC)[1];   // C2540  
}  
  
void func2(int n, int pC[]) {  
   int i = (pC)[1];   // OK  
}  
  
int main() {  
   int pC[100];  
   func(100, pC);  
   func2(100, pC);  
}  
```