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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 15099fd212c58df0369749a497a277ecb7f6987e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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