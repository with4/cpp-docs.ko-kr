---
title: "2.7.2.8 copyprivate | Microsoft Docs"
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
ms.assetid: c382348c-c785-45b2-8ee6-a66b76b97f3e
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.7.2.8 copyprivate
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

해당  **copyprivate** 절 private 변수를 사용 하 여 값 팀의 한 구성원에서 다른 구성원으로 방송 하는 메커니즘을 제공 합니다.  공유 변수 제공 \(각 수준에 서로 다른 변수를 필요로 합니다. 예를 들어, 있는 재귀\)에 어려운 때 공유 변수 값을 사용 하는 대신 것입니다.  **Copyprivate** 절에 나타날 수 있습니다만  **단일** 지시문입니다.  
  
 구문에는  **copyprivate** 절은 다음과 같습니다:  
  
```  
  
copyprivate(  
variable-list  
)  
  
```  
  
 효과  **copyprivate** 절에서 해당 변수 목록에서 변수 발생에 관련 된 구조화 된 블록의 실행 후는  **단일** 생성, 팀에 있는 스레드 중 장애물 구문 끝에 남아 있는 전에.  팀의 각 변수에 대 한 다른 모든 스레드가 다음의  *변수 목록*, 해당 변수 \(처럼 배정\) 생성의 구조화 된 블록을 실행 하는 스레드는 해당 변수의 값이 정의 됩니다.  
  
 제한에는  **copyprivate** 절은 다음과 같습니다:  
  
-   지정 된 변수는  **copyprivate** 절에 나타나야 합니다는  **개인** 또는  **firstprivate** 절을 동일한  **단일** 지시문입니다.  
  
-   경우는  **단일** 지시문에  **copyprivate** 절 병렬 영역에 동적 범위를 발견, 모든 변수에 지정 된는  **copyprivate** 절 바깥쪽 컨텍스트에서 private 이어야 합니다.  
  
-   지정 된 변수를  **copyprivate** 절에서 액세스할 수 있는 명확한 복사 할당 연산자에 있어야 합니다.