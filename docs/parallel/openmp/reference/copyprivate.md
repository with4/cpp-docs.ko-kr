---
title: "copyprivate | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "copyprivate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "copyprivate OpenMP clause"
ms.assetid: 02c0209d-abe8-4797-8365-a82b53c3f15d
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# copyprivate
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

하나 이상의 변수 모든 스레드 간에 공유 하도록 지정 합니다.  
  
## 구문  
  
```  
copyprivate(var)  
```  
  
## 설명  
 다음은 각 매개 변수에 대한 설명입니다.  
  
 `var`  
 공유 하려면 하나 이상의 변수입니다.  변수가 두 개 이상 지정 된 경우 변수 이름을 쉼표로 구분 합니다.  
  
## 설명  
 `copyprivate`적용 되는 [single](../../../parallel/openmp/reference/single.md) 지시문입니다.  
  
 자세한 내용은 [2.7.2.8 copyprivate](../../../parallel/openmp/2-7-2-8-copyprivate.md)를 참조하십시오.  
  
## 예제  
  
```  
// omp_copyprivate.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
float x, y, fGlobal = 1.0;  
#pragma omp threadprivate(x, y)  
  
float get_float() {  
   fGlobal += 0.001;  
   return fGlobal;  
}  
  
void use_float(float f, int t) {  
   printf_s("Value = %f, thread = %d\n", f, t);  
}  
  
void CopyPrivate(float a, float b) {  
   #pragma omp single copyprivate(a, b, x, y)   
   {  
      a = get_float();  
      b = get_float();  
      x = get_float();  
      y = get_float();  
    }  
  
   use_float(a, omp_get_thread_num());     
   use_float(b, omp_get_thread_num());     
   use_float(x, omp_get_thread_num());  
   use_float(y, omp_get_thread_num());  
}  
  
int main() {  
   float a = 9.99, b = 123.456;  
  
   printf_s("call CopyPrivate from a single thread\n");  
   CopyPrivate(9.99, 123.456);  
  
   printf_s("call CopyPrivate from a parallel region\n");  
   #pragma omp parallel       
   {  
      CopyPrivate(a, b);  
   }  
}  
```  
  
  **CopyPrivate 단일 스레드에서 호출**  
**값 1.001000, 스레드 \= 0 \=**  
**값 1.002000, 스레드 \= 0 \=**  
**값 1.003000, 스레드 \= 0 \=**  
**값 1.004000, 스레드 \= 0 \=**  
**CopyPrivate 병렬 영역에서 호출**  
**값 1.005000, 스레드 \= 0 \=**  
**값 1.005000, 스레드 \= \= 1**  
**값 1.006000, 스레드 \= 0 \=**  
**값 1.006000, 스레드 \= \= 1**  
**값 1.007000, 스레드 \= 0 \=**  
**값 1.007000, 스레드 \= \= 1**  
**값 1.008000, 스레드 \= 0 \=**  
**값 1.008000, 스레드 \= \= 1**   
## 참고 항목  
 [Clauses](../../../parallel/openmp/reference/openmp-clauses.md)