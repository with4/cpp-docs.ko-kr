---
title: "컴파일러 오류 C3022 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3022
dev_langs:
- C++
helpviewer_keywords:
- C3022
ms.assetid: 9f1d444c-6c6e-48d9-9346-69128390aa33
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 87e2f9257a1f3a6b3083129dfc6e2b0e005dc986
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3022"></a>컴파일러 오류 C3022
'clause': OpenMP 'directive' 지시문에서 'value'의 예약 종류가 잘못되었습니다.  
  
 지원되지 않는 값이 절에 전달되었습니다.  
  
 다음 샘플에서는 C3022를 생성합니다.  
  
```  
// C3022.cpp  
// compile with: /openmp /link vcomps.lib  
#include <stdio.h>  
#include "omp.h"  
  
int main() {  
   int i;  
  
   #pragma omp parallel for schedule(10)   // C3022  
   for (i = 0; i < 10; ++i) ;  
  
   #pragma omp parallel for schedule(x)   // C3022  
   for (i = 0; i < 10; ++i) ;  
  
   // OK  
   #pragma omp parallel for schedule(runtime)  
   for (i = 0; i < 10; ++i)  
   ;  
}  
```
