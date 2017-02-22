---
title: "OMP_DYNAMIC | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "OMP_DYNAMIC"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OMP_DYNAMIC OpenMP environment variable"
ms.assetid: e306049d-b644-4b73-8b63-46c835bff98b
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# OMP_DYNAMIC
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

실행 시간 OpenMP 병렬 영역에 스레드 수를 조정할 수 있는지 여부를 지정 합니다.  
  
## 구문  
  
```  
set OMP_DYNAMIC[=TRUE | =FALSE]  
```  
  
## 설명  
 `OMP_DYNAMIC` 환경 변수를 재정의 하 여 해당 [omp\_set\_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md) 함수입니다.  
  
 OpenMP 표준은 Visual C\+\+ 구현에서 기본값은 `OMP_DYNAMIC=FALSE`.  
  
 자세한 내용은 [4.3 OMP\_DYNAMIC](../../../parallel/openmp/4-3-omp-dynamic.md)를 참조하십시오.  
  
## 예제  
 다음 명령 집합을 `OMP_DYNAMIC` 환경 변수를 true로.  
  
```  
set OMP_DYNAMIC=TRUE  
```  
  
 다음 명령을 한 현재 설정을 표시 하는 `OMP_DYNAMIC` 환경 변수:  
  
```  
set OMP_DYNAMIC  
```  
  
## 참고 항목  
 [Environment Variables](../../../parallel/openmp/reference/openmp-environment-variables.md)