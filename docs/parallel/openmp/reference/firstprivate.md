---
title: "firstprivate | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "firstprivate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "firstprivate OpenMP clause"
ms.assetid: db479766-6d3b-4bbd-b28e-b192d826788c
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# firstprivate
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

병렬 구문을 전에 있기 때문에 각 스레드가 자체 인스턴스 변수를 했는지와 변수의 값으로 변수를 초기화 해야 함을 지정 합니다.  
  
## 구문  
  
```  
firstprivate(var)  
```  
  
#### 매개 변수  
  
|Parameter|설명|  
|---------------|--------|  
|`var`|병렬 구문을 전에 있기 때문에 각 스레드 및 해당 인스턴스를 변수 변수 값으로 초기화 됩니다.  변수가 두 개 이상 지정 된 경우 변수 이름을 쉼표로 구분 합니다.|  
  
## 설명  
  
## 설명  
 `firstprivate`다음 지시문에 적용 됩니다.  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [sections](../../../parallel/openmp/reference/sections-openmp.md)  
  
-   [single](../../../parallel/openmp/reference/single.md)  
  
 자세한 내용은 [2.7.2.2 firstprivate](../../../parallel/openmp/2-7-2-2-firstprivate.md)를 참조하십시오.  
  
## 예제  
 사용 하는 예제에 대 한 `firstprivate`, 예제를 참조 하십시오 [private](../../../parallel/openmp/reference/private-openmp.md).  
  
## 참고 항목  
 [Clauses](../../../parallel/openmp/reference/openmp-clauses.md)