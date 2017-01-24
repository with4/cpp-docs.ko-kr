---
title: "2.6.6 ordered Construct | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 5b3c1ba5-cfb8-4b05-865b-f446ae1c9f7c
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.6.6 ordered Construct
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

구조화 된 블록 다음에  **주문** 지시문에 반복 됩니다 실행 됩니다 연속 루프에서 순서 대로 실행 됩니다.  구문에는  **주문** 지시문은 다음과 같습니다:  
  
```  
#pragma omp ordered new-line  
   structured-block  
```  
  
 **주문** 지시문의 동적 범위 내 이어야는  **에 대 한** 또는  **에 대 한 병렬** 생성.  **에 대 한** 또는  **병렬에 대 한** 지시문을  **주문** 바인딩 구문이 있어야는  **주문** 절에 설명 된 대로 지정 된  [섹션 2.4.1](../../parallel/openmp/2-4-1-for-construct.md) 페이지 11.  실행의  **에 대 한** 또는  **에 대 한 병렬** 로 구성는  **주문** 절을  **주문** 구문을 실행 엄격 합니다 수 실행 루프를 순차 실행의 순서에서.  
  
 제한에는  **주문** 지시어는 다음과 같습니다.  
  
-   루프를 반복은  **에 대 한** 구문을 동일한 순서가 지정 된 지시문 두 번 이상 실행 합니다 않는 및 두 개 이상의 실행 해야 합니다  **주문** 지시문입니다.