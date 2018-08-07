---
title: 컴파일러 오류 C3052 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3052
dev_langs:
- C++
helpviewer_keywords:
- C3052
ms.assetid: 87480c42-1ceb-4775-8d20-88c54a7bb6a6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 96db942b0ed50114378843b9f88fd77b2d24d771
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33244200"
---
# <a name="compiler-error-c3052"></a>컴파일러 오류 C3052
'var': default(none) 절 밑의 데이터 공유 절에 변수가 없습니다.  
  
 [default(none)](../../parallel/openmp/reference/default-openmp.md) 가 사용되는 경우 구조화된 블록에 사용되는 모든 변수가 [shared](../../parallel/openmp/reference/shared-openmp.md) 또는 [private](../../parallel/openmp/reference/private-openmp.md)으로 명시적으로 지정되어야 합니다.  
  
 다음 샘플에서는 C3052를 생성합니다.  
  
```  
// C3052.cpp  
// compile with: /openmp /c  
int main() {  
   int n1 = 1;  
  
   #pragma omp parallel default(none) // shared(n1) private(n1)  
   {  
      n1 = 0;   // C3052 use either a shared or private clause  
   }  
}  
```