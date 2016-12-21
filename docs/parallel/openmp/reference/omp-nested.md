---
title: "OMP_NESTED | Microsoft Docs"
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
  - "OMP_NESTED"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OMP_NESTED OpenMP environment variable"
ms.assetid: c43f5287-a548-40d0-bd54-0c6b2b9f9a53
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OMP_NESTED
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

중첩 된 병렬 처리 활성화 또는 비활성화를 하지 않으면 중첩 된 병렬 처리를 사용할지 여부를 지정 `omp_set_nested`.  
  
## 구문  
  
```  
set OMP_NESTED[=TRUE | =FALSE]  
```  
  
## 설명  
 `OMP_NESTED` 환경 변수를 재정의 하 여 해당 [omp\_set\_nested](../../../parallel/openmp/reference/omp-set-nested.md) 함수입니다.  
  
 OpenMP 표준은 Visual C\+\+ 구현에서 기본값은 `OMP_DYNAMIC=FALSE`.  
  
 자세한 내용은 [4.4 OMP\_NESTED](../../../parallel/openmp/4-4-omp-nested.md)를 참조하십시오.  
  
## 예제  
 다음 명령 집합을 `OMP_NESTED` 환경 변수를 true로.  
  
```  
set OMP_NESTED=TRUE  
```  
  
 다음 명령을 한 현재 설정을 표시 하는 `OMP_NESTED` 환경 변수:  
  
```  
set OMP_NESTED  
```  
  
## 참고 항목  
 [Environment Variables](../../../parallel/openmp/reference/openmp-environment-variables.md)