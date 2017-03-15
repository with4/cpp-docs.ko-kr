---
title: "2.8 Directive Binding | Microsoft Docs"
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
ms.assetid: 7bdac45e-ab55-42f0-bd47-a2e3d5bbab3e
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.8 Directive Binding
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

지시문의 동적 바인딩은 다음과 같은 규칙을 준수 해야 합니다.  
  
-   **에 대 한**,  **섹션**,  **단일**,  **마스터**, 및  **장벽** 지시문에 바깥쪽 동적으로 바인딩할  **병렬**, 1의 값에 관계 없이 존재 하는 경우  **경우** 절 지시문에 존재할 수 있습니다.  병렬 영역이 현재 실행 되 고 있으면 해당 지시문의 마스터 스레드 구성 된 팀에서 실행 됩니다.  
  
-   **주문** 지시문에 바깥쪽 동적으로 바인딩된  **에 대 한**.  
  
-   **원자** 지시문을 단독에 비해 적용  **원자** 지시문에서 모든 스레드를 현재 팀 뿐 아니라.  
  
-   **중요 한** 지시문을 단독에 비해 적용  **중요 한** 지시문에서 모든 스레드를 현재 팀 뿐 아니라.  
  
-   지시문은 모든 지시어는 가장 가까운 바깥쪽 동적으로 바인딩할 수 있습니다 포함  **병렬**.