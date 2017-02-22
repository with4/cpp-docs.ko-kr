---
title: "컴파일러 경고 (수준 1) C4028 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4028"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4028"
ms.assetid: c3e8b70b-e870-416c-a285-bba5f71dbfc6
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# 컴파일러 경고 (수준 1) C4028
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

형식 매개 변수 'number'이\(가\) 선언과 다릅니다.  
  
 형식 매개 변수의 형식이 선언에 있는 해당 매개 변수와 다릅니다.  원래 선언의 형식이 사용됩니다.  
  
 이 경고는 C 소스 코드에 대해서만 유효합니다.  
  
## 예제  
 다음 샘플에서는 C4028 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4028.c  
// compile with: /W1 /Za  
void f(int , ...);  
void f(int i, int j) {}   // C4028  
  
void g(int , int);  
void g(int i, int j) {}   // OK  
  
int main() {}  
```