---
title: 컴파일러 오류 C3010 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3010
dev_langs:
- C++
helpviewer_keywords:
- C3010
ms.assetid: e959d038-bba6-432a-9c0a-0470474de7d9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3421a7611bd7e749670c62e52526e296fd3f6c14
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33242061"
---
# <a name="compiler-error-c3010"></a>컴파일러 오류 C3010
'label': OpenMP 구조화된 블록 내부에서 외부로 점프할 수 없습니다.  
  
 코드가 OpenMP 블록 안이나 밖으로 점프할 수 없습니다.  
  
 다음 샘플에서는 C3010을 생성합니다.  
  
```  
// C3010.c  
// compile with: /openmp  
int main() {  
   #pragma omp parallel   
   {  
      #pragma omp parallel  
      {  
         goto lbl3;  
      }  
   }  
   lbl3:;   // C3010  
}  
```