---
title: "컴파일러 오류 C3031 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3031
dev_langs:
- C++
helpviewer_keywords:
- C3031
ms.assetid: 7e621e7e-eda7-45b5-8836-29599cd05255
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 3ddf6809081cae78d0280c57f9ecc156f82e2821
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3031"></a>컴파일러 오류 C3031
'var': 'reduction' 절의 변수는 스칼라 산술 형식이어야 합니다.  
  
 잘못된 형식의 변수가 reduction 절에 전달되었습니다.  
  
 다음 샘플에서는 C3031을 생성합니다.  
  
```  
// C3031.cpp  
// compile with: /openmp /link vcomps.lib  
#include <stdio.h>  
#include "omp.h"  
  
typedef struct {  
   int n;  
} Incomplete;  
  
extern Incomplete inc;  
int i = 9;  
  
int main() {  
   #pragma omp parallel reduction(+: inc)   // C3031   
      ;  
  
   #pragma omp parallel reduction(+: i)     // OK  
      ;  
}  
```
