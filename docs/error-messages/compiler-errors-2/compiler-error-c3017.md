---
title: "컴파일러 오류 C3017 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3017
dev_langs:
- C++
helpviewer_keywords:
- C3017
ms.assetid: 12ab2c2a-d0d2-4900-9cbf-39be0af590dd
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 02e90c911c7210b4e2260bed1f843c0f4ecc891e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3017"></a>컴파일러 오류 C3017
OpenMP 'for' 문의 종료 테스트 형식이 잘못되었습니다.  
  
 OpenMP 문의 `for` 루프를 완벽하고 명시적으로 지정해야 합니다.  
  
 다음 샘플에서는 C3017을 생성합니다.  
  
```  
// C3017.cpp  
// compile with: /openmp  
int main()  
{  
   int i = 0, j = 10;  
  
   #pragma omp parallel  
   {  
      #pragma omp for  
      for (i = 0; i; ++i)   // C3017  
      // Try the following line instead:  
      // for (i = 0; i < 10; ++i)  
         ;  
   }  
}  
```