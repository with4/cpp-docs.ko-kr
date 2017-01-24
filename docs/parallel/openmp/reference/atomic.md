---
title: "atomic | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "atomic"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "atomic OpenMP directive"
ms.assetid: 275e0338-cf2f-4525-97b5-696250000df7
caps.latest.revision: 11
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# atomic
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

지정 하는 자동으로 업데이트 되는 메모리 위치입니다.  
  
## 구문  
  
```  
#pragma omp atomic  
   expression  
```  
  
#### 매개 변수  
 `expression`  
 Lvalue 메모리 위치를 포함 하는 문에 여러 개의 쓰기에 대해 보호 하려는.  올바른 식 양식에 대 한 자세한 내용은 OpenMP 사양을 참조 하십시오.  
  
## 설명  
 `atomic` 지시문 OpenMP 절을 지원 합니다.  
  
 자세한 내용은 [2.6.4 atomic Construct](../../../parallel/openmp/2-6-4-atomic-construct.md)를 참조하십시오.  
  
## 예제  
  
```  
// omp_atomic.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
#define MAX 10  
  
int main() {  
   int count = 0;  
   #pragma omp parallel num_threads(MAX)  
   {  
      #pragma omp atomic  
      count++;  
   }  
   printf_s("Number of threads: %d\n", count);  
}  
```  
  
  **스레드 수: 10**   
## 참고 항목  
 [OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)