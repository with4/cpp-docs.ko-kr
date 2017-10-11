---
title: "컴파일러 오류 C2164 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2164
dev_langs:
- C++
helpviewer_keywords:
- C2164
ms.assetid: 55df5024-68a8-45a8-ae6c-e6dba35318a2
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 2a60b263dad350a0c2e28d3d20053ff10f128e24
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2164"></a>컴파일러 오류 C2164
'function': 내장 함수를 선언 하지  
  
 `intrinsic` pragma는 선언 되지 않은 함수를 사용 (에서만 발생 **/Oi**). 또는 헤더 파일을 포함 하지 않고 컴파일러 내장 함수 중 하나를 사용 했습니다.  
  
 다음 샘플에서는 C2164 오류가 생성 됩니다.  
  
```  
// C2164.c  
// compile with: /c  
// processor: x86  
// Uncomment the following line to resolve.  
// #include "xmmintrin.h"  
void b(float *p) {  
   _mm_load_ss(p);   // C2164  
}  
```
