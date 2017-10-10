---
title: "컴파일러 오류 C3046 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3046
dev_langs:
- C++
helpviewer_keywords:
- C3046
ms.assetid: 2e53d835-faa1-4ec0-9807-41f3dc552635
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: faeb97b8588731340bc40dfbd53a64fe7e96a77c
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3046"></a>컴파일러 오류 C3046
OpenMP '#pragma omp sections' 영역에 구조화된 블록이 없습니다.  
  
 [섹션](../../parallel/openmp/reference/sections-openmp.md) 지시문에 빈 코드 블록이 있습니다.  
  
 다음 샘플에서는 C3046을 생성합니다.  
  
```  
// C3046.cpp  
// compile with: /openmp /c  
#include "omp.h"  
  
int main() {  
   int n2 = 2, n3 = 3;  
  
   #pragma omp parallel  
   {  
      ++n2;  
  
      #pragma omp sections  
      {  
/*  
         ++n2;  
  
         #pragma omp section  
         {  
            ++n3;  
         }  
*/  
       }   // C3046 uncomment code to resolve this C3046  
   }  
}  
```
