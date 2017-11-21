---
title: "컴파일러 오류 C3004 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3004
dev_langs: C++
helpviewer_keywords: C3004
ms.assetid: 819c2b57-8366-4ca7-9135-1f0c5e5b6bb6
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6468ecdf001789a487658d80d50bc843e2df8e96
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3004"></a>컴파일러 오류 C3004
'clause': OpenMP 'directive' 지시문의 절이 잘못되었습니다.  
  
 OpenMP 절이 활성화되지 않은 지시문에서 사용되었습니다.  
  
 다음 샘플에서는 C3004를 생성합니다.  
  
```  
// C3004.c  
// compile with: /openmp  
int main()  
{  
   int x, y, z;  
  
   // Shared clause not allowed for 'single' directive.  
   #pragma omp single shared(x, y)   // C3004  
  
   x = y;  
}  
```