---
title: "컴파일러 오류 C3038 | Microsoft Docs"
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
  - "C3038"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3038"
ms.assetid: 140ada3e-5636-43ef-a4ee-22a9f66a771f
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3038
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var': 'private' 절의 변수는 바깥쪽 컨텍스트에서 환산\(reduction\) 변수일 수 없습니다.  
  
 병렬 지시문의 [reduction](../../parallel/openmp/reference/reduction.md) 절에 표시되는 변수는 병렬 구문에 바인딩하는 작업 공유 지시문의 [private](../../parallel/openmp/reference/private-openmp.md) 절에 지정할 수 없습니다.  
  
 다음 샘플에서는 C3038을 생성합니다.  
  
```  
// C3038.cpp // compile with: /openmp /c int g_i, g_i2; int main() { int i; #pragma omp parallel reduction(+: g_i) { #pragma omp for private(g_i)   // C3038 // try the following line instead // #pragma omp for private(g_i2) for (i = 0; i < 10; ++i) g_i += i; } }  
```