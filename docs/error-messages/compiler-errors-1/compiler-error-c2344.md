---
title: "컴파일러 오류 C2344 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2344"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2344"
ms.assetid: a84c7b37-c84e-4345-8691-c23abb2dc193
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2344
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

align\(\#\): 맞춤은 2의 거듭제곱이어야 합니다.  
  
 [align](../../cpp/align-cpp.md) 키워드를 사용하는 경우 전달하는 값이 2의 거듭제곱이어야 합니다.  
  
 예를 들어 3은 2의 거듭제곱이 아니므로 다음 코드는 C2344를 생성합니다.  
  
```  
// C2344.cpp // compile with: /c __declspec(align(3)) int a;   // C2344 __declspec(align(4)) int b;   // OK  
```