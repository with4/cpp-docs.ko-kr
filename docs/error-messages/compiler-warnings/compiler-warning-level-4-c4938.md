---
title: "컴파일러 경고 (수준 4) C4938 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4938
dev_langs:
- C++
helpviewer_keywords:
- C4938
ms.assetid: 6acac81a-9d23-465e-b700-ed4b6e8edcd0
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
ms.openlocfilehash: f4e3184d1833da65c73149eb89ab1be8b2249b4e
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-4-c4938"></a>컴파일러 경고(수준 4) C4938
'var': /fp:strict 또는 #pragma fenv_access를 지정하면 부동 소수점 환산(reduction) 변수로 인해 일관성 없는 결과가 발생할 수 있습니다.  
  
 사용 하지 않아야 [/fp: strict](../../build/reference/fp-specify-floating-point-behavior.md) 또는 [fenv_access](../../preprocessor/fenv-access.md) 으로 OpenMP 부동 소수점 많이 줄여 합계가 다른 순서로 계산 되므로 합니다. 따라서 결과가 /openmp를 사용하지 않을 경우의 결과와 다를 수 있습니다.  
  
 다음 샘플에서는 C4938을 생성합니다.  
  
```  
// C4938.cpp  
// compile with: /openmp /W4 /fp:strict /c  
// #pragma fenv_access(on)  
extern double *a;   
  
double test(int first, int last) {   
   double sum = 0.0;   
   #pragma omp parallel for reduction(+: sum)   // C4938  
   for (int i = first ; i <= last ; ++i)   
      sum += a[i];   
   return sum;   
}  
```  
  
 명시적 병렬화를 사용하지 않을 경우 합계는 다음과 같이 계산됩니다.  
  
```  
sum = a[first] + a[first + 1] + ... + a[last];   
```  
  
 명시적 병렬화(및 두 개의 스레드)를 사용할 경우 합계는 다음과 같이 계산됩니다.  
  
```  
sum1 = a[first] + ... a[first + last / 2];   
sum2 = a[(first + last / 2) + 1] + ... a[last];   
sum = sum1 + sum2;  
```
