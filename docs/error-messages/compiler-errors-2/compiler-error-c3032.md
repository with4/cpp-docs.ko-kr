---
title: 컴파일러 오류 C3032 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3032
dev_langs:
- C++
helpviewer_keywords:
- C3032
ms.assetid: 6a92bd8e-319f-4a99-aef4-a9021f6f9928
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e4882887964ef707c955f5b7532aa13eec0077e2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3032"></a>컴파일러 오류 C3032
'var': 'clause' 절의 변수는 불완전한 형식 'type'이 될 수 없습니다.  
  
 특정 절에 전달되는 형식은 컴파일러에 완벽하게 표시되어야 합니다.  
  
 다음 샘플에서는 C3032를 생성합니다.  
  
```  
// C3032.cpp  
// compile with: /openmp /link vcomps.lib  
#include "omp.h"  
  
struct Incomplete;  
extern struct Incomplete inc;  
  
int main() {  
   int i = 9;  
   #pragma omp parallel private(inc)   // C3032  
      ;  
  
   #pragma omp parallel private(i)     // OK  
      ;  
  
}  
```