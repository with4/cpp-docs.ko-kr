---
title: "lastprivate | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "lastprivate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "lastprivate OpenMP clause"
ms.assetid: 6ef87b31-375a-47e8-8d0d-281be45fb56a
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# lastprivate
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

변수는 바깥쪽 컨텍스트에서 버전의 최종 반복 \(for 루프 구문\) 이나 마지막 구역 \(\# pragma 섹션\) 어떤 스레드가 실행 전용 버전을 같게 설정 되도록 지정 합니다.  
  
## 구문  
  
```  
lastprivate(var)  
```  
  
## 설명  
 다음은 각 매개 변수에 대한 설명입니다.  
  
 `var`  
 최종 반복 \(for 루프 구문\) 이나 마지막 구역 \(\# pragma 섹션\) 개인 버전의 어떤 스레드 수로 설정 하는 변수를 실행 합니다.  
  
## 설명  
 `lastprivate`다음 지시문에 적용 됩니다.  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [sections](../../../parallel/openmp/reference/sections-openmp.md)  
  
 자세한 내용은 [2.7.2.3 lastprivate](../../../parallel/openmp/2-7-2-3-lastprivate.md)를 참조하십시오.  
  
## 예제  
 참조 하십시오 [schedule](../../../parallel/openmp/reference/schedule.md) 를 사용 하는 예에 대 한 `lastprivate` 절.  
  
## 참고 항목  
 [Clauses](../../../parallel/openmp/reference/openmp-clauses.md)