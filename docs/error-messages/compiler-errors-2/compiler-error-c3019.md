---
title: "컴파일러 오류 C3019 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3019
dev_langs:
- C++
helpviewer_keywords:
- C3019
ms.assetid: 31a6d9b6-d29f-4499-9ad8-48dd751e87c7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d9fcf1797fc24cff514fa927be98eeeeac66f907
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3019"></a>컴파일러 오류 C3019
openmp에서 'for' 문의 증분 형식이 잘못 되었습니다.  
  
 OpenMP의 증가식 부분 `for` 루프는 연산자의 왼쪽 및 오른쪽에 모두 인덱스 변수를 사용 해야 합니다.  
  
 다음 샘플에서는 C3019 오류가 생성 됩니다.  
  
```  
// C3019.cpp  
// compile with: /openmp  
int main()  
{  
   int i = 0, j = 1, n = 3;  
  
   #pragma omp parallel  
   {  
      #pragma omp for  
      for (i = 0; i < 10; i = j + n)   // C3019  
      // Try the following line instead:  
      // for (i = 0; i < 10; i++)  
         j *= 2;  
   }  
}  
```