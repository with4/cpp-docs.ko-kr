---
title: "컴파일러 경고 (수준 3) C4018 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4018"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4018"
ms.assetid: 6e8cbb04-d914-4319-b431-cbc2fbe40eb1
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 3) C4018
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'expression' : signed 또는 unsigned가 일치하지 않습니다.  
  
 부호 있는 숫자와 부호 없는 숫자를 비교하려면 부호 있는 값을 부호 없는 값으로 변환해야 합니다.  
  
 이 경고는 부호 있는 형식과 부호 없는 형식을 테스트할 때 두 형식 중 하나를 캐스팅하여 해결할 수 있습니다.  
  
 다음 샘플에서는 C4018 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4018.cpp  
// compile with: /W3  
int main() {  
   unsigned int uc = 0;  
   int c = 0;  
   unsigned int c2 = 0;  
  
   if (uc < c) uc = 0;   // C4018  
  
   // OK  
   if (uc == c2) uc = 0;  
}  
```