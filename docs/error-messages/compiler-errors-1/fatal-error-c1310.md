---
title: 심각한 오류 C1310 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1310
dev_langs:
- C++
helpviewer_keywords:
- C1310
ms.assetid: ac48aa51-8023-42fe-b844-3f8bf228fbef
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c226b61dd722eb4ed32de6c8885c575b64ba2448
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33226493"
---
# <a name="fatal-error-c1310"></a>심각한 오류 C1310
OpenMP에서는 프로필 기반 최적화를 사용할 수 없습니다.  
  
 [/GL](../../build/reference/ltcg-link-time-code-generation.md) 로 컴파일된 모든 모듈을 [/LTCG:PGI](../../build/reference/gl-whole-program-optimization.md)와 연결할 수 없습니다.  
  
 다음 샘플에서는 C1310을 생성합니다.  
  
```  
// C1310.cpp  
// compile with: /openmp /GL /link /LTCG:PGI  
// C1310 expected  
int main()  
{  
   int i = 0, j = 10;  
  
   #pragma omp parallel  
   {  
      #pragma omp for  
      for (i = 0; i < 0; i++)   
         --j;  
   }  
}  
```