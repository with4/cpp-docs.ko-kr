---
title: "2.4.2 sections Construct | Microsoft Docs"
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
ms.assetid: e9e6e3ea-7fc9-4925-8f68-92b8a5bb1e76
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.4.2 sections Construct
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**섹션** 지시문 일련의 팀에서 스레드 간에 나눌 수 있는 구문 지정 noniterative 작업 공유 구조를 식별 합니다.  각 구역은 한 번 팀의 스레드에 의해 실행 됩니다.  구문에는  **섹션** 지시문은 다음과 같습니다:  
  
```  
#pragma omp sections [clause[[,] clause] ...] new-line  
   {  
   [#pragma omp section new-line]  
      structured-block  
   [#pragma omp section new-line  
      structured-block ]  
...  
}  
```  
  
 절에서 다음 중 하나입니다.  
  
 **개인 \(** *변수 목록* **\)**  
  
 **firstprivate \(** *변수 목록* **\)**  
  
 **lastprivate \(** *변수 목록* **\)**  
  
 **reduction\(** *operator* **:**  *variable\-list* **\)**  
  
 **에 nowait**  
  
 각 섹션에서 앞에  **섹션** 지시문을 있지만  **섹션** 지시문이 첫 번째 구역에 대 한 선택적입니다.  **섹션** 지시문의 어휘 범위 내에서 표시 되어야의  **섹션** 지시문입니다.  끝에 있는 암시적 장애물입니다.는  **섹션** 하지 않으면 생성 한  **에 nowait** 지정 된.  
  
 제한에는  **섹션** 지시어는 다음과 같습니다.  
  
-   A  **섹션** 지시문의 어휘 범위 밖에 표시 해야를  **섹션** 지시문입니다.  
  
-   단일  **에 nowait** 절에 나타날 수는  **섹션** 지시문입니다.  
  
## 상호 참조:  
  
-   **개인**,  **firstprivate**,  **lastprivate**, 및  **감소** 절을 참조 하십시오.  [2.7.2 섹션](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) 25 페이지입니다.