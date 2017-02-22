---
title: "컴파일러 경고 (수준 1) C4717 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4717"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4717"
ms.assetid: 5ef3c6c7-8599-4714-a973-0f5b69cdab3c
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 1) C4717
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 모든 제어 경로에서 재귀적입니다. 함수로 인해 런타임 스택 오버플로가 발생합니다.  
  
 함수를 통한 모든 경로에는 함수에 대한 호출이 포함되어 있습니다.  먼저 함수를 재귀적으로 호출하는 방법 외에 함수를 종료하는 방법이 없으므로 함수는 종료되지 않습니다.  
  
 다음 샘플에서는 C4717 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4717.cpp  
// compile with: /W1 /c  
// C4717 expected  
int func(int x) {  
   if (x > 1)  
      return func(x - 1); // recursive call  
   else {  
      int y = func(0) + 1; // recursive call  
      return y;  
   }  
}  
  
int main(){  
   func(1);  
}  
```