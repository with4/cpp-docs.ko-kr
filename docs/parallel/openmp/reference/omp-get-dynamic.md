---
title: "omp_get_dynamic | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "omp_get_dynamic"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_get_dynamic OpenMP function"
ms.assetid: efa843c5-7266-4a75-8db3-22992663d9db
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# omp_get_dynamic
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

실행된 시간에 따라 후속 병렬 영역에서 사용할 수 있는 스레드 수를 조정할 수 있는 경우를 나타내는 값을 반환 합니다.  
  
## 구문  
  
```  
int omp_get_dynamic();  
```  
  
## 반환 값  
 0이 아닌 경우, 스레드의 동적 조정 가능 합니다.  
  
## 설명  
 동적 조정 스레드로 지정 된 [omp\_set\_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md) 및 [OMP\_DYNAMIC](../../../parallel/openmp/reference/omp-dynamic.md).  
  
 자세한 내용은 [3.1.7 omp\_set\_dynamic Function](../../../parallel/openmp/3-1-7-omp-set-dynamic-function.md)를 참조하십시오.  
  
## 예제  
 참조 하십시오 [omp\_set\_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md) 를 사용 하는 예에 대 한 `omp_get_dynamic`.  
  
## 참고 항목  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)