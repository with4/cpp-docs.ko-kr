---
title: "컴파일러 오류 C3053 | Microsoft Docs"
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
  - "C3053"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3053"
ms.assetid: ab9a25f3-e341-4f6e-8e69-069b4a963a64
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3053
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbol': 'threadprivate'는 글로벌 또는 정적 데이터 항목에만 사용할 수 있습니다.  
  
 [threadprivate](../../parallel/openmp/reference/threadprivate.md)에 전달된 기호는 전역 또는 정적이어야 합니다.  
  
 다음 샘플에서는 C3053을 생성합니다.  
  
```  
// C3053.cpp // compile with: /openmp void Test() { int x, y; #pragma omp threadprivate(x, y)   // C3053 #pragma omp parallel copyin(x, y) { x = y; } }  
```  
  
 해결 방법:  
  
```  
// C3053b.cpp // compile with: /openmp /LD int x, y; #pragma omp threadprivate(x, y) void Test() { #pragma omp parallel copyin(x, y) { x = y; } }  
```