---
title: "컴파일러 오류 C3039 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3039
dev_langs: C++
helpviewer_keywords: C3039
ms.assetid: 02776f16-f57a-4ffd-b7f7-9c696b633e08
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 35cf503199939b502840c840e55bb2e5579f116a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3039"></a>컴파일러 오류 C3039
'var': OpenMP 'for' 문의 인덱스 변수는 환산(reduction) 변수가 될 수 없습니다.  
  
 인덱스 변수는 암시적으로 전용 변수이므로 [환산(reduction)](../../parallel/openmp/reference/reduction.md) 절의 바깥쪽 [병렬](../../parallel/openmp/reference/parallel.md) 지시문에 사용할 수 없습니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C3039를 생성합니다.  
  
```  
// C3039.cpp  
// compile with: /openmp /c  
int g_i;  
  
int main() {  
   int i;  
  
   #pragma omp parallel reduction(+: i)  
   {  
      #pragma omp for  
      for (i = 0; i < 10; ++i)   // C3039  
         g_i += i;  
   }  
}  
```