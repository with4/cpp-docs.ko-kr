---
title: "컴파일러 경고(수준 1) C4080 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4080"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4080"
ms.assetid: 964fb3f4-b9fd-450b-aa23-35cece126172
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고(수준 1) C4080
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

세그먼트 이름에 대한 식별자가 있어야 하는데 'symbol'이 있습니다.  
  
 [\#pragma alloc\_text](../../preprocessor/alloc-text.md)의 세그먼트 이름은 문자열 또는 식별자여야 합니다. 유효한 식별자가 없으면 컴파일러가 pragma를 무시합니다.  
  
 다음 샘플에서는 C4080을 생성합니다.  
  
```  
// C4080.cpp // compile with: /W1 extern "C" void func(void); #pragma alloc_text()   // C4080 // try this line to resolve the warning // #pragma alloc_text("mysection", func) int main() { } void func(void) { }  
```