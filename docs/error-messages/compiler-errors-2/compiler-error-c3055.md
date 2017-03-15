---
title: "컴파일러 오류 C3055 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3055"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3055"
ms.assetid: 60446ee0-18dd-48fc-9059-f0a14229dce8
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 오류 C3055
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbol': 'threadprivate' 지시문에 사용된 기호만 참조할 수 있습니다.  
  
 기호가 참조된 다음 [threadprivate](../../parallel/openmp/reference/threadprivate.md) 절에서 사용되며 이는 허용되지 않습니다.  
  
 다음 샘플에서는 C3055를 생성합니다.  
  
```  
// C3055.cpp // compile with: /openmp int x, y; int z = x; #pragma omp threadprivate(x, y)   // C3055 void test() { #pragma omp parallel copyin(x, y) { x = y; } }  
```  
  
 해결 방법:  
  
```  
// C3055b.cpp // compile with: /openmp /LD int x, y, z; #pragma omp threadprivate(x, y) void test() { #pragma omp parallel copyin(x, y) { x = y; } }  
```