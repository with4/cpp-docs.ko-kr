---
title: "컴파일러 오류 C3048 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3048
dev_langs:
- C++
helpviewer_keywords:
- C3048
ms.assetid: 48e07091-94d9-471d-befe-7e2507631edd
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: a17a103bf49040496b886799bf58910eedff8051
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3048"></a>컴파일러 오류 C3048
'#pragma omp atomic' 다음에 나오는 식의 형식이 잘못되었습니다.  
  
 원자성 지시문이 잘못 지정되었습니다.  
  
 다음 샘플에서는 C3048을 생성합니다.  
  
```  
// C3048.cpp  
// compile with: /openmp vcomps.lib  
#include "omp.h"  
#include <stdio.h>  
  
int main() {  
   int a[10];  
   omp_set_num_threads(4);  
   #pragma omp parallel  
   {  
      #pragma omp atomic  
      a[0] = 1;   // C3048  
      // try the following line instead  
      // a[0] += 1;  
   }  
}  
```
