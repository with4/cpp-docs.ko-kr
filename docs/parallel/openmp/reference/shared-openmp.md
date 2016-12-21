---
title: "shared (OpenMP) | Microsoft Docs"
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
  - "Shared"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "shared OpenMP clause"
ms.assetid: 7887dc95-67a2-462f-a3a2-8e0632bf5d04
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# shared (OpenMP)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

하나 이상의 변수 모든 스레드 간에 공유 하도록 지정 합니다.  
  
## 구문  
  
```  
shared(var)  
```  
  
## 설명  
 다음은 각 매개 변수에 대한 설명입니다.  
  
 `var`  
 공유 하는 하나 보다 더 많은 변수입니다.  변수가 두 개 이상 지정 된 경우 변수 이름을 쉼표로 구분 합니다.  
  
## 설명  
 스레드 간에 변수를 공유할 수 있는 것은 [copyprivate](../../../parallel/openmp/reference/copyprivate.md) 절.  
  
 `shared`다음 지시문에 적용 됩니다.  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [sections](../../../parallel/openmp/reference/sections-openmp.md)  
  
 자세한 내용은 [2.7.2.4 shared](../../../parallel/openmp/2-7-2-4-shared.md)를 참조하십시오.  
  
## 예제  
 참조 하십시오 [private](../../../parallel/openmp/reference/private-openmp.md) 를 사용 하는 예에 대 한 `shared`.  
  
## 참고 항목  
 [Clauses](../../../parallel/openmp/reference/openmp-clauses.md)