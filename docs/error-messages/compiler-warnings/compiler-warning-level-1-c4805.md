---
title: "컴파일러 경고(수준 1) C4805 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4805"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4805"
ms.assetid: 99c7b7e2-272e-4ab5-8580-17c42e62e2ef
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고(수준 1) C4805
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operation': 연산에 'type' 형식과 'type' 형식을 함께 사용하는 것은 안전하지 않습니다.  
  
 이 경고는 [bool](../../cpp/bool-cpp.md)과 [int](../../c-language/integer-types.md) 간의 비교 작업에 대해 생성됩니다. 다음 샘플에서는 C4805를 생성합니다.  
  
```  
// C4805.cpp // compile with: /W1 int main() { int i = 1; bool b = true; if (i == b) {   // C4805, comparing bool and int variables } }  
```