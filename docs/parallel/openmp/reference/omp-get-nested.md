---
title: "omp_get_nested | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "omp_get_nested"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_get_nested OpenMP function"
ms.assetid: e9784847-516e-40d3-89f7-b8b6898d8667
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# omp_get_nested
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

중첩 된 병렬 처리 가능 여부를 나타내는 값을 반환 합니다.  
  
## 구문  
  
```  
int omp_get_nested( );  
```  
  
## 반환 값  
 0이 아닌 경우 중첩 된 병렬 처리를 사용할 수 있습니다.  
  
## 설명  
 중첩 된 병렬 처리로 지정 된 [omp\_set\_nested](../../../parallel/openmp/reference/omp-set-nested.md) 및 [OMP\_NESTED](../../../parallel/openmp/reference/omp-nested.md).  
  
 자세한 내용은 [3.1.10 omp\_get\_nested Function](../../../parallel/openmp/3-1-10-omp-get-nested-function.md)를 참조하십시오.  
  
## 예제  
 참조 하십시오 [omp\_set\_nested](../../../parallel/openmp/reference/omp-set-nested.md) 를 사용 하는 예에 대 한 `omp_get_nested`.  
  
## 참고 항목  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)