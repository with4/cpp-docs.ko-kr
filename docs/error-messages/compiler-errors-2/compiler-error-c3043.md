---
title: "컴파일러 오류 C3043 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3043
dev_langs:
- C++
helpviewer_keywords:
- C3043
ms.assetid: 0ef55e63-e82b-48eb-9d44-690950ac34c6
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: b3ba534b9b605b34290180c9f5d495c94e9d2b88
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3043"></a>컴파일러 오류 C3043
OpenMP 'critical' 지시문은 같은 이름의 'critical' 지시문 내부에 중첩될 수 없습니다.  
  
 A [중요](../../parallel/openmp/reference/critical.md) 지시문 내부에 중첩 될 수 없습니다는 `critical` 지시문에 같은 이름을 사용 합니다.  
  
 다음 샘플에서는 C3043을 생성합니다.  
  
```  
// C3043.cpp  
// compile with: /openmp /c  
#include "omp.h"  
  
int main() {  
   int n1 = 1, n2 = 2, n3 = 3;  
  
   #pragma omp parallel  
   {  
      ++n2;  
  
      #pragma omp critical(MyTest)  
      {  
         ++n2;  
  
         #pragma omp critical(MyTest)   // C3043  
         // try the following line instead  
         // #pragma omp critical(MyTest2)  
         {  
            ++n3;  
         }  
      }  
   }  
}  
```
