---
title: "컴파일러 오류 C3012 | Microsoft Docs"
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
  - "C3012"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3012"
ms.assetid: cc7040b1-b3fb-4da6-a474-877914d30332
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3012
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'intrinsic': 병렬 영역 내부에서는 직접 내장 함수를 사용할 수 없습니다.  
  
 [컴파일러 내장](../../intrinsics/compiler-intrinsics.md) 함수는 `omp``parallel` 지역에서 사용할 수 없습니다.  
  
 다음 샘플에서는 C3012를 생성합니다.  
  
```  
// C3012.cpp // compile with: /openmp #ifdef __cplusplus extern "C" { #endif void* _ReturnAddress(); #ifdef __cplusplus } #endif int main() { _ReturnAddress();   // OK #pragma omp parallel { _ReturnAddress();   // C3012 } }  
```