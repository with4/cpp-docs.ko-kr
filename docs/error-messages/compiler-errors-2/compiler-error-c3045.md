---
title: "컴파일러 오류 C3045 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3045
dev_langs:
- C++
helpviewer_keywords:
- C3045
ms.assetid: 9351ba3e-3d3f-455f-ac90-a810fa9fd947
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 99974cf55ae6fe73c1bc51f3f9f2b20268381e16
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3045"></a>컴파일러 오류 C3045
OpenMP 'sections' 지시문 다음에는 복합 문이 와야 합니다. '{'가 없습니다.  
  
 괄호로 구분된 코드 블록이 [sections](../../parallel/openmp/reference/sections-openmp.md) 지시문 뒤에 나와야 합니다.  
  
 다음 샘플에서는 C3045를 생성합니다.  
  
```  
// C3045.cpp  
// compile with: /openmp /c  
#include "omp.h"  
  
int main() {  
   int n2 = 2, n3 = 3;  
  
   #pragma omp parallel  
   {  
      ++n2;  
  
      #pragma omp sections  
         ++n2;   // C3045  
  
      #pragma omp sections   // OK  
      {  
         ++n3;  
      }  
   }  
}  
```
