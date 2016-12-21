---
title: "3.2 Lock Functions | Microsoft Docs"
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
ms.assetid: 0ec855c6-55a9-49d7-bee4-5edae6e86a1b
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.2 Lock Functions
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 섹션에서 설명 하는 기능은 동기화에 사용 되는 잠금 조작 합니다.  
  
 다음 기능에 대 한 잠금 변수 형식이 있어야 합니다  **omp\_lock\_t**.  이 변수는 이러한 기능을 통해 액세스 되어야 합니다.  잠금 함수 포인터에 인수 해야  **omp\_lock\_t** 형식입니다.  
  
-   `omp_init_lock` 함수는 단순 잠금을 초기화 합니다.  
  
-   `omp_destroy_lock` 함수는 단순 잠금을 제거 합니다.  
  
-   `omp_set_lock` 함수를 단순 잠금을 사용할 수 있을 때까지 기다립니다.  
  
-   `omp_unset_lock` 함수는 단순 잠금을 해제 합니다.  
  
-   `omp_test_lock` 함수 테스트는 단순 잠금을 합니다.  
  
 다음 기능에 대 한 잠금 변수 형식이 있어야 합니다  **omp\_nest\_lock\_t**.  이 변수는 이러한 기능을 통해 액세스 되어야 합니다.  Nestable lock 함수 포인터에 인수 해야  **omp\_nest\_lock\_t** 형식입니다.  
  
-   `omp_init_nest_lock` 함수를 nestable 잠금을 초기화 합니다.  
  
-   `omp_destroy_nest_lock` Nestable 잠금 함수는 제거 합니다.  
  
-   `omp_set_nest_lock` 함수를 nestable 잠금을 사용할 수 있을 때까지 기다립니다.  
  
-   `omp_unset_nest_lock` 함수를 nestable 잠금을 해제 합니다.  
  
-   `omp_test_nest_lock` Nestable lock을 테스트 하는 함수입니다.  
  
 OpenMP 잠금 기능 lock 변수는 항상 읽고 최신 잠금 변수 값을 업데이트 하는 방법에 액세스할.  따라서 명시적으로 포함 하는 OpenMP 프로그램에 대 한 필요는 없습니다  **플러시** 지시문 잠금 변수 값을 여러 스레드 간에 일치 하는지 확인 합니다.  \(만들 필요가 있을 수 있습니다  **플러시** 지시문을 다른 변수 값을 일치 시킬 수 있습니다.\)