---
title: "2.7.2 Data-Sharing Attribute Clauses | Microsoft Docs"
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
ms.assetid: 47347d3c-18bd-441f-99cf-7737564c417f
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.7.2 Data-Sharing Attribute Clauses
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

여러 개의 지시문 지역 기간 동안 공유 특성 변수를 제어할 수 있게 하는 절을 적용 합니다.  공유 특성 절 절 나타나는 지시문의 어휘 범위 변수에 적용 됩니다.  다음 절 중에 모든 지시문을 사용할 수 있습니다.  목록의 특정 지시문에 잘못 된 지시문에 설명 되어 있습니다.  
  
 볼 때 병렬 변수인 작업 공유 생성자를 발견 한 공유 특성 절에 변수를 지정 하지 경우 또는  **threadprivate** 지시문을 다음 변수에 공유 됩니다.  동적 범위를 병렬 영역 내에서 선언 된 정적 변수를 공유할 수 있습니다.  힙에 할당 된 메모리 \(예를 들어,를 사용 하 여  **malloc \(\)** 은 C 나 C\+\+ 나는  **새** C\+\+에서 연산자\) 공유 하는.  \(이 메모리에 대 한 포인터, 전용 또는 공유 수 있습니다.\) 자동 저장 기간 동적 범위를 병렬 영역 내에서 선언 된 변수를 private입니다.  
  
 대부분의 절에 동의  *변수 목록* 볼 수 있는 변수 목록을 쉼표로 구분 된 인수입니다.  변수에서 참조 하는 경우 특성 데이터 공유 절에 템플릿에서 파생 형식이 있는 및 프로그램에서 변수를 다른 참조가 있는, 동작이 정의 되지 않습니다.  
  
 지시문 절 내에서 표시 되는 모든 변수 표시 되어야 합니다.  절 필요에 따라 반복 될 수 있습니다 있지만 변수 모두에서 지정 될 수 있습니다 제외 하 고 하나 이상의 절에 변수를 지정할 수 있습니다 한  **firstprivate** a  **lastprivate** 절.  
  
 다음 단원에서는 특성 데이터 공유 절에 설명합니다.  
  
-   **개인**,  [섹션 2.7.2.1](../../parallel/openmp/2-7-2-1-private.md) 25 페이지입니다.  
  
-   **firstprivate**,  [섹션 2.7.2.2](../../parallel/openmp/2-7-2-2-firstprivate.md) 26 페이지에 있습니다.  
  
-   **lastprivate**,  [섹션 2.7.2.3](../../parallel/openmp/2-7-2-3-lastprivate.md) 27 페이지에 있습니다.  
  
-   **공유**,  [섹션 2.7.2.4](../../parallel/openmp/2-7-2-4-shared.md) 27 페이지에 있습니다.  
  
-   **기본**,  [섹션 2.7.2.5](../../parallel/openmp/2-7-2-5-default.md) 28 페이지에 있습니다.  
  
-   **감소**,  [섹션 2.7.2.6](../../parallel/openmp/2-7-2-6-reduction.md) 28 페이지에 있습니다.  
  
-   **copyin**,  [섹션 2.7.2.7](../../parallel/openmp/2-7-2-7-copyin.md) 31 페이지에 있습니다.  
  
-   **copyprivate**,  [섹션 2.7.2.8](../../parallel/openmp/2-7-2-8-copyprivate.md) 32 페이지에 있습니다.