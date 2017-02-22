---
title: "omp_unset_nest_lock | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "omp_unset_nest_lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_unset_nest_lock OpenMP function"
ms.assetid: 1721d061-3f9c-45d7-b479-a665cd0a121d
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# omp_unset_nest_lock
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Nestable 잠금을 해제합니다.  
  
## 구문  
  
```  
void omp_unset_nest_lock(   
   omp_nest_lock_t *lock   
);  
```  
  
## 설명  
 다음은 각 매개 변수에 대한 설명입니다.  
  
 `lock`  
 형식의 변수를 [omp\_nest\_lock\_t](../../../parallel/openmp/reference/omp-nest-lock-t.md) 로 초기화 된 [omp\_init\_nest\_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md), 스레드에 의해 소유를 함수에서 실행 합니다.  
  
## 설명  
 자세한 내용은 [3.2.4 omp\_unset\_lock and omp\_unset\_nest\_lock Functions](../../../parallel/openmp/3-2-4-omp-unset-lock-and-omp-unset-nest-lock-functions.md)를 참조하십시오.  
  
## 예제  
 참조 하십시오 [omp\_init\_nest\_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md) 를 사용 하는 예에 대 한 `omp_unset_nest_lock`.  
  
## 참고 항목  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)