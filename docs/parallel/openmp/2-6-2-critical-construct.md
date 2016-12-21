---
title: "2.6.2 critical Construct | Microsoft Docs"
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
ms.assetid: c46ecd00-b4a2-4a5e-ba92-288c329e773a
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.6.2 critical Construct
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**중요 한** 지시문 구문 관련 된 구조화 된 블록의 실행을 한 번에 단일 스레드로 제한 식별 합니다.  구문에는  **중요 한** 지시문은 다음과 같습니다:  
  
```  
#pragma omp critical [(name)]  new-line  
   structured-block  
```  
  
 선택적인  *이름* 중요 한 영역을 식별 하는 데 사용할 수 있습니다.  외부 링크를 사용 하 고 레이블, 태그, 멤버 및 일반 식별자로 사용 되는 이름 공간에서 다른 이름 공간에 있는 중요 한 영역을 식별 하는 데 사용 되는 식별자.  
  
 \(프로그램\)의 모든 중요 한 영역 이름이 같은 다른 스레드에서 실행 될 때까지 스레드가 임계 영역의 시작 부분에 대기 합니다.  이름 없는 모든  **중요 한** 지시문 같은 알 수 없는 이름에 매핑합니다.