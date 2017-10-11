---
title: "컴파일러 오류 C3042 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3042
dev_langs:
- C++
helpviewer_keywords:
- C3042
ms.assetid: bf73f61e-5bd2-40a8-9b06-6244e6a15a41
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: f0fe35a4021cca6ac1e3dd9846a3c165f50797f4
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3042"></a>컴파일러 오류 C3042
OpenMP 'directive' 절에 'copyprivate'와 'nowait' 절을 함께 사용할 수 없습니다.  
  
 [copyprivate](../../parallel/openmp/reference/copyprivate.md) 및 [nowait](../../parallel/openmp/reference/nowait.md) 절은 지정된 지시문에서 함께 사용할 수 없습니다. 이 오류를 해결하려면 `copyprivate` 또는 `nowait` 절 중 하나 또는 둘 다를 제거합니다.  
  
 다음 샘플에서는 C3042를 생성합니다.  
  
```  
// C3042.cpp  
// compile with: /openmp /c  
#include <stdio.h>  
#include "omp.h"  
  
double d;  
  
int main() {  
    #pragma omp parallel private(d)  
   {  
      #pragma omp single copyprivate(d) nowait   // C3042  
      {  
      }  
   }  
}  
```
