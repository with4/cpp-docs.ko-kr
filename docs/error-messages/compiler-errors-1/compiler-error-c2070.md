---
title: "컴파일러 오류 C2070 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2070"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2070"
ms.assetid: 4c8dea63-1227-4aba-be26-2462537f86fb
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2070
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type': sizeof 피연산자가 잘못되었습니다.  
  
 [sizeof](../../cpp/sizeof-operator.md) 연산자에 식이나 형식 이름이 필요합니다.  
  
 다음 샘플에서는 C2070 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2070.cpp  
void func() {}  
int main() {  
   int a;  
   a = sizeof(func);   // C2070  
}  
```  
  
 다음과 같이 해결할 수 있습니다.  
  
```  
// C2070b.cpp  
void func() {}  
int main() {  
   int a;  
   a = sizeof(a);  
}  
```