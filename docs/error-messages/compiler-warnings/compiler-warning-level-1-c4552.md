---
title: "컴파일러 경고 (수준 1) C4552 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4552"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4552"
ms.assetid: ebbbb5ee-1c19-45bd-b386-41a19630fc76
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 경고 (수준 1) C4552
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator' : 의미 없는 연산자입니다. 파생 작업이 있는 연산자여야 합니다.  
  
 표현문에 있는 연산자를 수행한 결과로 식의 위에서처럼 파생 작업이 일어나지 않으면 이는 잘못된 작업입니다.  
  
 이 경고를 해결하려면 식을 괄호 안에 넣으십시오.  
  
 다음 샘플에서는 C4552 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4552.cpp  
// compile with: /W1  
int main() {  
   int i, j;  
   i + j;   // C4552  
   // try the following line instead  
   // (i + j);  
}  
```