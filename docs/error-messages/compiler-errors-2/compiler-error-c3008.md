---
title: "컴파일러 오류 C3008 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3008
dev_langs:
- C++
helpviewer_keywords:
- C3008
ms.assetid: 04d93201-28e5-4be0-945c-aad616376f4b
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
ms.openlocfilehash: ce31f82e869329a41af1493792d47e8c937c80eb
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3008"></a>컴파일러 오류 C3008
'arg': OpenMP 'directive' 지시문의 인수에 닫는 ')'가 없습니다.  
  
 인수를 사용하는 OpenMP 지시문에 닫는 괄호가 없습니다.  
  
 다음 샘플에서는 C3008을 생성합니다.  
  
```  
// C3008.c  
// compile with: /openmp  
int main()  
{  
   int x, y, z;  
   #pragma omp parallel shared(x   // C3008  
   // Try the following line instead:  
   #pragma omp parallel shared(x)  
   {  
   }  
}  
```
