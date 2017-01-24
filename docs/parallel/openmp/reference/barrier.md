---
title: "barrier | Microsoft Docs"
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
  - "barrier"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "barrier OpenMP directive"
ms.assetid: 5c73ad4f-c768-443a-8f9e-4fd8bc2253c7
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# barrier
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

팀에서 모든 스레드를 동기화 합니다. 장애물 모든 스레드가 실행 될 때까지 모든 스레드는 장애물에 일시 중지 합니다.  
  
## 구문  
  
```  
#pragma omp barrier  
```  
  
## 설명  
 `barrier` 지시문 OpenMP 절을 지원 합니다.  
  
 자세한 내용은 [2.6.3 barrier Directive](../../../parallel/openmp/2-6-3-barrier-directive.md)를 참조하십시오.  
  
## 예제  
 샘플을 사용 하는 방법에 대 한 `barrier`를 참조 하십시오 [master](../../../parallel/openmp/reference/master.md).  
  
## 참고 항목  
 [Directives](../../../parallel/openmp/reference/openmp-directives.md)