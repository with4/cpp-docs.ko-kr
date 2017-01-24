---
title: "copyin | Microsoft Docs"
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
  - "copyin"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "copyin OpenMP clause"
ms.assetid: 369efa88-613c-4cb1-9e11-7b9ee08a4b25
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# copyin
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

마스터 스레드 값에 액세스 하는 스레드 수는 [threadprivate](../../../parallel/openmp/reference/threadprivate.md) 변수입니다.  
  
## 구문  
  
```  
copyin(var)  
```  
  
## 설명  
 다음은 각 매개 변수에 대한 설명입니다.  
  
 `var`  
 `threadprivate` 변수 병렬 구성 하기 전에 적용 되는 마스터 스레드 변수 값으로 초기화 됩니다.  
  
## 설명  
 `copyin`다음 지시문에 적용 됩니다.  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [sections](../../../parallel/openmp/reference/sections-openmp.md)  
  
 자세한 내용은 [2.7.2.7 copyin](../../../parallel/openmp/2-7-2-7-copyin.md)를 참조하십시오.  
  
## 예제  
 참조 하십시오 [threadprivate](../../../parallel/openmp/reference/threadprivate.md) 를 사용 하는 예에 대 한 `copyin`.  
  
## 참고 항목  
 [Clauses](../../../parallel/openmp/reference/openmp-clauses.md)