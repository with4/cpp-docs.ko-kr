---
title: "컴파일러 경고 (수준 1) C4553 | Microsoft Docs"
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
  - "C4553"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4553"
ms.assetid: d8aacbe0-3cb5-4367-a6e5-fd7e28f0ff9d
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4553
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator' : 의미 없는 연산자입니다. 'operator'을\(를\) 사용하려고 했습니까?  
  
 표현문에 있는 연산자를 수행한 결과로 식의 위에서처럼 파생 작업이 일어나지 않으면 이는 잘못된 작업입니다.  
  
 다음 샘플에서는 C4553 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4553.cpp  
// compile with: /W1  
int func()  
{  
   return 0;  
}  
  
int main()  
{  
   int i;  
   i == func();   // C4553  
   // try the following line instead  
   // i = func();  
}  
```