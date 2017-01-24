---
title: "컴파일러 경고 (수준 1) C4558 | Microsoft Docs"
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
  - "C4558"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4558"
ms.assetid: 52bb0324-7bec-468c-b35b-13a08d38e578
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4558
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

피연산자의 값 'value'이\(가\) 'lowerbound \- upperbound' 범위를 벗어났습니다.  
  
 어셈블리 언어 명령에 전달한 값이 매개 변수에 대해 지정된 범위를 벗어났으므로  값이 잘립니다.  
  
 다음 샘플에서는 C4558 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4558.cpp  
// compile with: /W1  
// processor: x86  
void asm_test() {  
   __asm pinsrw   mm1, eax, 8;   // C4558  
}  
  
int main() {  
}  
```