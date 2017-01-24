---
title: "컴파일러 경고(수준 1) C4167 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4167"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4167"
ms.assetid: 74a420bd-9371-4167-b1ee-74dd8680f97b
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고(수준 1) C4167
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

function: 내장 함수로만 사용할 수 있습니다.  
  
 **\#pragma 함수**는 컴파일러에서 내장 형식으로 사용해야 하는 함수에 대해 기존 호출을 사용하도록 강제하려고 합니다. pragma가 무시됩니다.  
  
 이 경고를 방지하려면 **\#pragma 함수**를 제거합니다.  
  
## 예제  
  
```  
// C4167.cpp // compile with: /W1 #include <malloc.h> #pragma function(_alloca )   // C4167: _alloca() is intrinsic only int main(){}  
```