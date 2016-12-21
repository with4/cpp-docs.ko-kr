---
title: "컴파일러 오류 C3039 | Microsoft Docs"
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
  - "C3039"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3039"
ms.assetid: 02776f16-f57a-4ffd-b7f7-9c696b633e08
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3039
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var': OpenMP 'for' 문의 인덱스 변수는 환산\(reduction\) 변수가 될 수 없습니다.  
  
 인덱스 변수는 암시적으로 전용 변수이므로 [환산\(reduction\)](../../parallel/openmp/reference/reduction.md) 절의 바깥쪽 [병렬](../../parallel/openmp/reference/parallel.md) 지시문에 사용할 수 없습니다.  
  
## 예제  
 다음 샘플에서는 C3039를 생성합니다.  
  
```  
// C3039.cpp // compile with: /openmp /c int g_i; int main() { int i; #pragma omp parallel reduction(+: i) { #pragma omp for for (i = 0; i < 10; ++i)   // C3039 g_i += i; } }  
```