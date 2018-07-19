---
title: 컴파일러 오류 C3044 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3044
dev_langs:
- C++
helpviewer_keywords:
- C3044
ms.assetid: 9f3e25b2-4676-49ab-97bf-6c88cd0fa377
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 61021438711544bb9e6489855f8bcb46a867a1d4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33252113"
---
# <a name="compiler-error-c3044"></a>컴파일러 오류 C3044
'section' : OpenMP 'sections' 지시문 내부에 직접 중첩되어야 합니다.  
  
 컴파일러에서 `section` 지시문이 잘못 사용된 것을 발견했습니다. 자세한 내용은 [섹션](../../parallel/openmp/reference/sections-openmp.md)을 참조하세요.  
  
 다음 샘플에서는 C3044를 생성합니다.  
  
```  
// C3044.cpp  
// compile with: /openmp /c  
#include "omp.h"  
int main() {  
   int n2 = 2, n3 = 3;  
  
   #pragma omp parallel  
   {  
      ++n2;  
  
      #pragma omp sections  
      {  
         ++n2;  
      }  
  
      #pragma omp section   // C3044  
      {  
         ++n3;  
      }  
   }  
  
   #pragma omp parallel  
   {  
      ++n2;  
  
      #pragma omp sections  
      {  
         #pragma omp section   // OK  
         {  
            ++n3;  
         }  
      }  
   }  
}  
```