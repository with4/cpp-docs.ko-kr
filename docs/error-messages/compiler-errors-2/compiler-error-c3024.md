---
title: 컴파일러 오류 C3024 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3024
dev_langs:
- C++
helpviewer_keywords:
- C3024
ms.assetid: 1c031c28-ce37-4de3-aead-cfe76b261856
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 63d9b39c280be627effd2d66c86f06f45e532ac7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33242946"
---
# <a name="compiler-error-c3024"></a>컴파일러 오류 C3024
'schedule(runtime)' : chunk_size 식은 허용되지 않습니다.  
  
 schedule 절의 런타임 매개 변수에 값을 전달할 수 없습니다.  
  
 다음 샘플에서는 C3024를 생성합니다.  
  
```  
// C3024.cpp  
// compile with: /openmp /link vcomps.lib  
#include <stdio.h>  
#include "omp.h"  
  
int main() {  
   int i;  
  
   #pragma omp parallel for schedule(runtime, 10)   // C3024  
   for (i = 0; i < 10; ++i) ;  
  
   #pragma omp parallel for schedule(runtime)   // OK  
   for (i = 0; i < 10; ++i) ;  
}  
```