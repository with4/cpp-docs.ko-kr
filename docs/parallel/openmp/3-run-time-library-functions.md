---
title: "3. 런타임 라이브러리 함수 | Microsoft Docs"
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
ms.assetid: b226e512-6822-4cbe-a2ca-74cc2bb7e880
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3. 런타임 라이브러리 함수
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 섹션에서는 OpenMP C 및 c + + 런타임 라이브러리 함수에 설명 합니다. 헤더 **\< omp.h >** 두 가지 유형, 제어 및 병렬 실행 환경을 쿼리 및 데이터에 대 한 액세스를 동기화 하는 데 사용할 수 있는 함수를 잠그는 데 사용할 수 있는 여러 함수를 선언 합니다.  
  
 형식 **omp_lock_t** 또는 스레드는 잠금을 소유 하 고 형식인 개체 잠금 가능 않도록 표시할 수 있습니다. 이러한 잠금은 라고 *간단한 잠금을*합니다.  
  
 형식 **omp_nest_lock_t** 는 것을 표현할 수 있는 개체 형식의 잠금을 사용할 수 있는지 또는 잠금을 소유 하는 스레드의 id 및 *count 중첩* (아래 설명 참조). 이러한 잠금은 라고 *가능 잠금*합니다.  
  
 라이브러리 함수는 "C" 링크가 있는 외부 함수입니다.  
  
 이 장에서 설명 다음 항목으로 구분 됩니다.  
  
-   실행 환경 함수 (참조 [섹션 3.1](../../parallel/openmp/3-1-execution-environment-functions.md) 페이지 35).  
  
-   기능 잠금 (참조 [섹션 3.2](../../parallel/openmp/3-2-lock-functions.md) 41 페이지).