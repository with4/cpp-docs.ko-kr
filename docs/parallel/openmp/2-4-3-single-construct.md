---
title: "2.4.3 single Construct | Microsoft Docs"
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
ms.assetid: 15c180cd-e462-4b41-bf8c-cb8b1afb1a9b
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.4.3 single Construct
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

해당  **단일** 지시문 관련 된 구조화 된 블록 \(반드시 마스터 스레드\) 팀에서 하나의 스레드가 실행 되도록 지정 하는 구문을 나타냅니다.  구문에는  **단일** 지시문은 다음과 같습니다:  
  
```  
#pragma omp single [clause[[,] clause] ...] new-line  
   structured-block  
```  
  
 절에서 다음 중 하나입니다.  
  
 **개인 \(** *변수 목록* **\)**  
  
 **firstprivate \(** *변수 목록* **\)**  
  
 **copyprivate \(** *변수 목록* **\)**  
  
 **에 nowait**  
  
 되는 암시적 장벽 뒤는  **단일** 구성 하지 않으면는  **에 nowait** 절을 지정 합니다.  
  
 제한에는  **단일** 지시어는 다음과 같습니다.  
  
-   단일  **에 nowait** 절에 나타날 수 있는  **단일** 지시문.  
  
-   해당  **copyprivate** 와 절을 사용 해야 하지는  **에 nowait** 절.  
  
## 상호 참조:  
  
-   **개인**,  **firstprivate**, 및  **copyprivate** 절을 참조 하십시오.  [섹션 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) 25 페이지입니다.