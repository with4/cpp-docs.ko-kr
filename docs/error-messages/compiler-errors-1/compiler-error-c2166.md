---
title: "컴파일러 오류 C2166 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2166"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2166"
ms.assetid: 12789c3a-cc76-48bb-ae2e-64283e0964ed
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2166
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

l\-value가 const 개체를 지정합니다.  
  
 코드에서 `const`로 선언된 항목을 수정하려고 합니다.  
  
 다음 샘플에서는 C2166을 생성합니다.  
  
```  
// C2166.cpp int f(); int main() { ( (const int&) 1 ) = 5;   // C2166 }  
```