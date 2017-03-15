---
title: "4.1 OMP_SCHEDULE | Microsoft Docs"
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
ms.assetid: d0dce411-2351-4ee9-a1cc-c0322a58b65c
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 4.1 OMP_SCHEDULE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**OMP\_SCHEDULE** 에 적용 됩니다.  **에 대 한** 및  **에 대 한 병렬** 예약 유형이 있는 지시문  **런타임**.  인식 된 예약 유형 하 고 선택적으로이 환경 변수를 설정 하 여 이와 같은 순환 구조에 대 한 예약 종류와 청크 크기 런타임에 설정할 수 있습니다  *chunk\_size*.  
  
 에 대 한  **에 대 한** 및  **에 대 한 병렬** 이외의 다른 예약 유형을 가진 지시문  **런타임**,  **OMP\_SCHEDULE** 무시 됩니다.  기본값은 환경 변수의 구현 시 정의 됩니다.  경우 선택적  *chunk\_size* 설정, 값은 양수 여야 합니다.  경우  *chunk\_size* 1 가정, 설정 되어 있지 않은 경우를 제외 하 고는  **정적** 일정.  에  **정적** 일정을 기본 청크 크기 설정 되어 루프에 적용할 스레드 수를 나눈 루프 반복 공간입니다.  
  
 예를 들면 와 같은 형식입니다.  
  
```  
setenv OMP_SCHEDULE "guided,4"  
setenv OMP_SCHEDULE "dynamic"  
```  
  
## 상호 참조:  
  
-   **에 대 한** 지시문 참조  [섹션 2.4.1](../../parallel/openmp/2-4-1-for-construct.md) 11 페이지입니다.  
  
-   **에 대 한 병렬** 지시문을 참조  [섹션 2.5.1](../../parallel/openmp/2-5-1-parallel-for-construct.md) 16 페이지입니다.