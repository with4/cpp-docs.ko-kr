---
title: "컴파일러 오류 C3007 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3007
dev_langs:
- C++
helpviewer_keywords:
- C3007
ms.assetid: e415ef42-bdc9-4f32-8198-5e25b289a089
caps.latest.revision: 6
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
ms.openlocfilehash: 9bc22dfa00491c7ff4f1871fe494bd7719b1b802
ms.lasthandoff: 04/12/2017

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
