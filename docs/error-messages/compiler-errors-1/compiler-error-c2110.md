---
title: "컴파일러 오류 C2110 | Microsoft Docs"
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
  - "C2110"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2110"
ms.assetid: 48fd76ed-90d6-4a60-9c7b-f6ce9355b4ca
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2110
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'\+': 두 포인터를 더할 수 없습니다.  
  
 더하기\(`+`\) 연산자를 사용하여 두 포인터 값을 더하려고 했습니다.  
  
 다음 샘플에서는 C2110을 생성합니다.  
  
```  
// C2110.cpp int main() { int a = 0; int *pa; int *pb; a = pa + pb;   // C2110 }  
```