---
title: 컴파일러 오류 C3056 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3056
dev_langs:
- C++
helpviewer_keywords:
- C3056
ms.assetid: 9500173d-870b-49b3-8e88-0ee93586d19a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 52ec97865a1aa9c8b6da9b109bf100eb62824a9d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33249169"
---
# <a name="compiler-error-c3056"></a>컴파일러 오류 C3056
'symbol': 기호가 'threadprivate' 지시문과 같은 범위에 속하지 않습니다.  
  
 [threadprivate](../../parallel/openmp/reference/threadprivate.md) 절에서 사용되는 기호는 `threadprivate` 절과 동일한 범위에 있어야 합니다.  
  
 다음 샘플에서는 C3056을 생성합니다.  
  
```  
// C3056.cpp  
// compile with: /openmp  
int x, y;  
void test() {  
   #pragma omp threadprivate(x, y)   // C3056  
   #pragma omp parallel copyin(x, y)  
   {  
      x = y;  
   }  
}  
```  
  
 해결 방법:  
  
```  
// C3056b.cpp  
// compile with: /openmp /LD  
int x, y;  
#pragma omp threadprivate(x, y)  
void test() {  
   #pragma omp parallel copyin(x, y)  
   {  
      x = y;  
   }  
}  
```