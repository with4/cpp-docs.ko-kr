---
title: 컴파일러 오류 C3041 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3041
dev_langs:
- C++
helpviewer_keywords:
- C3041
ms.assetid: 9df1ae44-3ac7-4c6c-899f-f35ffe7ccf0d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 766536426a0b183299d5028d90197fd058fb6126
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3041"></a>컴파일러 오류 C3041
'var': 'copyprivate' 절의 변수는 바깥쪽 컨텍스트에서 private이어야 합니다.  
  
 [copyprivate](../../parallel/openmp/reference/copyprivate.md) 에 전달된 변수를 바깥쪽 컨텍스트에서 공유할 수 없습니다.  
  
 다음 샘플에서는 C3041을 생성합니다.  
  
```  
// C3041.cpp  
// compile with: /openmp /c  
#include "omp.h"  
double d;  
int main() {  
   #pragma omp parallel shared(d)  
   // try the following line instead  
   // #pragma omp parallel private(d)  
   {  
      // or don't make d copyprivate  
      #pragma omp single copyprivate(d)   // C3041  
      {  
      }  
   }  
}  
```