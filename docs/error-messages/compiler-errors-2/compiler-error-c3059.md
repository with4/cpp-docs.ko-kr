---
title: "컴파일러 오류 C3059 | Microsoft Docs"
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
  - "C3059"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3059"
ms.assetid: 57220324-8286-4cab-a1ab-45385eb1eae0
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3059
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var': 'threadprivate' 기호는 'clause' 절에서 사용할 수 없습니다.  
  
 [threadprivate](../../parallel/openmp/reference/threadprivate.md) 기호가 절에서 사용되었습니다.  
  
 다음 샘플에서는 C3059를 생성합니다.  
  
```  
// C3059.cpp // compile with: /openmp #include "omp.h" int x, y; #pragma omp threadprivate(x, y) int main() { #pragma omp parallel private(x, y)   // C3059 { x = y; } }  
```  
  
 해결 방법:  
  
```  
// C3059b.cpp // compile with: /openmp #include "omp.h" int x = 0, y = 0; int main() { #pragma omp parallel firstprivate(y) private(x) { x = y; } }  
```