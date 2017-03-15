---
title: "flush (OpenMP) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Flush"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "flush OpenMP directive"
ms.assetid: 150ca46e-d4f7-4423-b0a4-838df40aeb67
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# flush (OpenMP)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

모든 스레드가 같은 보기 모든 공유 객체에 대 한 메모리를 지정 합니다.  
  
## 구문  
  
```  
#pragma omp flush [(var)]  
```  
  
## 설명  
 다음은 각 매개 변수에 대한 설명입니다.  
  
 `var`\(선택적 요소\)  
 쉼표로 구분 된 목록 동기화 할 개체를 나타내는 변수입니다.  경우 `var` 지정 하지 않으면 모든 메모리는 플러시.  
  
## 설명  
 **플러시** 지시문 OpenMP 절을 지원 합니다.  
  
 자세한 내용은 [2.6.5 flush Directive](../../../parallel/openmp/2-6-5-flush-directive.md)를 참조하십시오.  
  
## 예제  
  
```  
// omp_flush.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
void read(int *data) {  
   printf_s("read data\n");  
   *data = 1;  
}  
  
void process(int *data) {  
   printf_s("process data\n");  
   (*data)++;  
}  
  
int main() {  
   int data;  
   int flag;  
  
   flag = 0;  
  
   #pragma omp parallel sections num_threads(2)  
   {  
      #pragma omp section  
      {  
         printf_s("Thread %d: ", omp_get_thread_num( ));  
         read(&data);  
         #pragma omp flush(data)  
         flag = 1;  
         #pragma omp flush(flag)  
         // Do more work.  
      }  
  
      #pragma omp section   
      {  
         while (!flag) {  
            #pragma omp flush(flag)  
         }  
         #pragma omp flush(data)  
  
         printf_s("Thread %d: ", omp_get_thread_num( ));  
         process(&data);  
         printf_s("data = %d\n", data);  
      }  
   }  
}  
```  
  
  **스레드 0: 데이터 읽기**  
**스레드 1: 데이터 처리**  
**데이터 \= 2**   
## 참고 항목  
 [Directives](../../../parallel/openmp/reference/openmp-directives.md)