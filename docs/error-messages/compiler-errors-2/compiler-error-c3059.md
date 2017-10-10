---
title: "컴파일러 오류 C3059 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3059
dev_langs:
- C++
helpviewer_keywords:
- C3059
ms.assetid: 57220324-8286-4cab-a1ab-45385eb1eae0
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: e51938cbea3b2ab1e65cf97dc515bb7f420cf272
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3059"></a>컴파일러 오류 C3059
'var': 'threadprivate' 기호는 'clause' 절에서 사용할 수 없습니다.  
  
 [threadprivate](../../parallel/openmp/reference/threadprivate.md) 기호가 절에서 사용되었습니다.  
  
 다음 샘플에서는 C3059를 생성합니다.  
  
```  
// C3059.cpp  
// compile with: /openmp  
#include "omp.h"  
int x, y;  
#pragma omp threadprivate(x, y)  
  
int main() {  
   #pragma omp parallel private(x, y)   // C3059  
   {  
      x = y;  
   }  
}  
```  
  
 해결 방법:  
  
```  
// C3059b.cpp  
// compile with: /openmp  
#include "omp.h"  
int x = 0, y = 0;  
  
int main() {  
   #pragma omp parallel firstprivate(y) private(x)  
   {  
      x = y;  
   }  
}  
```
