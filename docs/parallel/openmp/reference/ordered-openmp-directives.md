---
title: "ordered (OpenMP Directives) | Microsoft Docs"
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
  - "ordered"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ordered OpenMP directive"
ms.assetid: e1aa703e-d07d-4f6a-9b2a-f4f25203d850
caps.latest.revision: 9
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ordered (OpenMP Directives)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

아래는 병렬화 된 코드를 지정 합니다 순차 루프 다음과 같이 루프를 실행 해야 합니다.  
  
## 구문  
  
```  
#pragma omp ordered  
   structured-block  
```  
  
## 설명  
 **주문** 지시문의 동적 범위 안에 있어야는 [for](../../../parallel/openmp/reference/for-openmp.md) 또는  **에 대 한 병렬** 로 구성는  **주문** 절.  
  
 **주문** 지시문 OpenMP 절을 지원 합니다.  
  
 자세한 내용은 [2.6.6 ordered Construct](../../../parallel/openmp/2-6-6-ordered-construct.md)를 참조하십시오.  
  
## 예제  
  
```  
// omp_ordered.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
static float a[1000], b[1000], c[1000];  
  
void test(int first, int last)   
{  
    #pragma omp for schedule(static) ordered  
    for (int i = first; i <= last; ++i) {  
        // Do something here.  
        if (i % 2)   
        {  
            #pragma omp ordered   
            printf_s("test() iteration %d\n", i);  
        }  
    }  
}  
  
void test2(int iter)   
{  
    #pragma omp ordered  
    printf_s("test2() iteration %d\n", iter);  
}  
  
int main( )   
{  
    int i;  
    #pragma omp parallel  
    {  
        test(1, 8);  
        #pragma omp for ordered  
        for (i = 0 ; i < 5 ; i++)  
            test2(i);  
    }  
}  
```  
  
  **test \(\) 반복 1**  
**test \(\) 반복 3**  
**test \(\) 반복 5**  
**test \(\) 반복 7**  
**test2\(\) 반복 0**  
**test2\(\) 반복 1**  
**test2\(\) 반복 2**  
**test2\(\) 반복 3**  
**test2\(\) 반복 4**   
## 참고 항목  
 [Directives](../../../parallel/openmp/reference/openmp-directives.md)