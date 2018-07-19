---
title: 컴파일러 오류 C3007 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3007
dev_langs:
- C++
helpviewer_keywords:
- C3007
ms.assetid: e415ef42-bdc9-4f32-8198-5e25b289a089
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d1424683db17247c6e31d0d26bce31f420353968
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33262392"
---
# <a name="compiler-error-c3007"></a>컴파일러 오류 C3007
'arg': OpenMP 'directive' 지시문의 절이 인수를 사용하지 않습니다.  
  
 OpenMP 지시문에 인수가 있지만 지시문에서 인수를 사용하지 않습니다.  
  
 다음 샘플에서는 C3007을 생성합니다.  
  
```  
// C3007.c  
// compile with: /openmp  
int main()  
{  
   #pragma omp parallel for ordered(2)   // C3007  
}  
```