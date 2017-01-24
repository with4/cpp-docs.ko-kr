---
title: "omp_set_num_threads | Microsoft Docs"
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
  - "omp_set_num_threads"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_set_num_threads OpenMP function"
ms.assetid: dae0bf3f-cd7a-4413-89de-6149ac1f4fa7
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# omp_set_num_threads
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

재정의 하지 않으면 스레드 후속 병렬 영역에 설정 된 [num\_threads](../../../parallel/openmp/reference/num-threads.md) 절.  
  
## 구문  
  
```  
void omp_set_num_threads(  
   int num_threads  
);  
```  
  
## 설명  
 다음은 각 매개 변수에 대한 설명입니다.  
  
 `num_threads`  
 병렬 영역에 스레드 수입니다.  
  
## 설명  
 자세한 내용은 [3.1.1 omp\_set\_num\_threads Function](../../../parallel/openmp/3-1-1-omp-set-num-threads-function.md)를 참조하십시오.  
  
## 예제  
 참조 하십시오 [omp\_get\_num\_threads](../../../parallel/openmp/reference/omp-get-num-threads.md) 를 사용 하는 예에 대 한 `omp_set_num_threads`.  
  
## 참고 항목  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)