---
title: "컴파일러 경고(수준 4) C4127 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4127"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4127"
ms.assetid: f59ded9e-5227-45bd-ac43-2aa861581363
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# 컴파일러 경고(수준 4) C4127
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

조건식이 상수입니다.  
  
 `if` 문 또는 `while` 루프의 제어 식이 상수로 계산됩니다.`while` 루프의 제어 식이 상수인 경우 루프가 중간에 종료되므로 `while` 루프를 `for` 루프로 바꾸는 것이 좋습니다. 루프가 무한 반복되는\(예: `while(1)`\) `for` 루프의 초기화, 종료 테스트, 루프 증분을 생략하고 `for` 문의 중간에서 루프를 종료할 수 있습니다.  
  
 다음 샘플에서는 C4127을 생성합니다.  
  
```  
// C4127.cpp // compile with: /W4 #include <stdio.h> int main() { if (1 == 1) {}   // C4127 while (1) { break; }   // C4127 // OK for ( ; ; ) { printf("test\n"); break; } }  
```