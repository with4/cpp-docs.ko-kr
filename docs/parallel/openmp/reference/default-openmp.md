---
title: "default (OpenMP) | Microsoft Docs"
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
  - "default"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "default OpenMP clause"
  - "defaults, OpenMP clause"
ms.assetid: 96055106-a8f0-40b3-8319-e412b6e07bf8
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# default (OpenMP)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

병렬 영역에 unscoped 변수 동작을 지정합니다.  
  
## 구문  
  
```  
default(shared | none)  
```  
  
## 설명  
 `shared`에 적용 된 경우는 `default` 절이 지정 되지 함께 지정 된 경우 병렬 영역에 있는 변수를 처리는 [shared](../../../parallel/openmp/reference/shared-openmp.md) 절.  `none`즉, 사용 범위는 병렬 영역에 사용 되는 모든 변수는 [private](../../../parallel/openmp/reference/private-openmp.md), [shared](../../../parallel/openmp/reference/shared-openmp.md), [reduction](../../../parallel/openmp/reference/reduction.md), [firstprivate](../../../parallel/openmp/reference/firstprivate.md), 또는 [lastprivate](../../../parallel/openmp/reference/lastprivate.md) 절 컴파일러 오류가 발생 합니다.  
  
 `default`다음 지시문에 적용 됩니다.  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [sections](../../../parallel/openmp/reference/sections-openmp.md)  
  
 자세한 내용은 [2.7.2.5 default](../../../parallel/openmp/2-7-2-5-default.md)를 참조하십시오.  
  
## 예제  
 참조 하십시오 [private](../../../parallel/openmp/reference/private-openmp.md) 를 사용 하는 예에 대 한 `default`.  
  
## 참고 항목  
 [Clauses](../../../parallel/openmp/reference/openmp-clauses.md)