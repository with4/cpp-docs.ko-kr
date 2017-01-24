---
title: "OMP_SCHEDULE | Microsoft Docs"
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
  - "OMP_SCHEDULE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OMP_SCHEDULE OpenMP environment variable"
ms.assetid: 2295a801-e584-4d2f-826f-7ca4c88846a6
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OMP_SCHEDULE
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

동작을 수정 하는 [schedule](../../../parallel/openmp/reference/schedule.md) 절 때 `schedule(runtime)` 에 지정 된는 `for` 또는 `parallel for` 지시문.  
  
## 구문  
  
```  
set OMP_SCHEDULE[=type[,size]]  
```  
  
## 설명  
 다음은 각 매개 변수에 대한 설명입니다.  
  
 `size`\(선택적 요소\)  
 반복의 크기를 지정합니다.  `size`양의 정수 여야 합니다.  기본 경우를 제외 하 고 1이 `type` 정적입니다.  Not valid when `type` is `runtime`.  
  
 `type`  
 일정 관리의 종류:  
  
-   `dynamic`  
  
-   `guided`  
  
-   `runtime`  
  
-   `static`  
  
## 설명  
 OpenMP 표준은 Visual C\+\+ 구현에서 기본값은 `OMP_SCHEDULE=static,0`.  
  
 자세한 내용은 [4.1 OMP\_SCHEDULE](../../../parallel/openmp/4-1-omp-schedule.md)를 참조하십시오.  
  
## 예제  
 다음 명령 집합을  **OMP\_SCHEDULE** 환경 변수:  
  
```  
set OMP_SCHEDULE="guided,2"  
```  
  
 다음 명령을 한 현재 설정을 표시 하는  **OMP\_SCHEDULE** 환경 변수:  
  
```  
set OMP_SCHEDULE  
```  
  
## 참고 항목  
 [Environment Variables](../../../parallel/openmp/reference/openmp-environment-variables.md)