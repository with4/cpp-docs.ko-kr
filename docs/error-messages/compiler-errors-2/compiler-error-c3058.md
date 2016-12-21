---
title: "컴파일러 오류 C3058 | Microsoft Docs"
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
  - "C3058"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3058"
ms.assetid: 669d08c8-0b58-4351-88aa-c6e6e1af481c
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3058
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbol': 기호를 'copyin' 절에 사용하기 전에 'threadprivate'로 선언하지 않았습니다.  
  
 기호를 먼저 [threadprivate](../../parallel/openmp/reference/threadprivate.md)로 선언해야 [copyin](../../parallel/openmp/reference/copyin.md) 절에 사용할 수 있습니다.  
  
 다음 샘플에서는 C3058을 생성합니다.  
  
```  
// C3058.cpp // compile with: /openmp int x, y, z; #pragma omp threadprivate(x, z) void test() { #pragma omp parallel copyin(x, y)   // C3058 { } }  
```  
  
 해결 방법:  
  
```  
// C3058b.cpp // compile with: /openmp /LD int x, y, z; #pragma omp threadprivate(x, y) void test() { #pragma omp parallel copyin(x, y) { } }  
```