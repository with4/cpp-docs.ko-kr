---
title: "4. Environment Variables | Microsoft Docs"
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
ms.assetid: 4ec7ed81-e9ca-46a1-84f8-8f9ce4587346
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 4. Environment Variables
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OpenMP C 및 C\+\+ API 환경 변수 \(또는 해당 하는 플랫폼별 메커니즘\)이 장은 병렬 코드의 실행을 제어 합니다.  환경 변수 이름이 대문자 여야 합니다.  할당 된 값을 대\/소문자를 구분 하지 않는 고 선행 및 후행 공백이 있을 수 있습니다.  수정 프로그램이 시작 된 후의 값은 무시 됩니다.  
  
 환경 변수는 다음과 같습니다.  
  
-   **OMP\_SCHEDULE** 실행 시간 일정 유형 및 청크 크기를 설정 합니다.  
  
-   **OMP\_NUM\_THREADS** 실행 하는 동안 사용할 스레드 수를 설정 합니다.  
  
-   **OMP\_DYNAMIC** 동적 조정 스레드를 사용할지 여부.  
  
-   **OMP\_NESTED** 사용 하거나 중첩 된 병렬 처리를 사용 하지 않습니다.  
  
 이 장의 예에서는 어떻게 Unix C shell \(csh\) 환경에서는 이러한 변수가 설정 되었을 수 있습니다 방법을 보여 줍니다.  Korn 셸 및 DOS 환경에서는 동작 비슷한 같습니다.  
  
 csh:  
 setenv OMP\_SCHEDULE "동적"  
  
 ksh:  
 OMP\_SCHEDULE 내보내기 "동적" \=  
  
 DOS:  
 OMP\_SCHEDULE 설정 \= "동적"