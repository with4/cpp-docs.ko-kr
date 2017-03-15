---
title: "2.6.1 master Construct | Microsoft Docs"
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
ms.assetid: c092064b-ea57-4d4e-9c99-a004d65656fe
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.6.1 master Construct
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**마스터** 지시문을 마스터 팀의 스레드에서 실행 되는 구조화 된 블록 지정 구문 식별 합니다.  구문에는  **마스터** 지시문은 다음과 같습니다:  
  
```  
#pragma omp master new-line  
   structured-block  
```  
  
 팀의 다른 스레드 관련 된 구조화 된 블록을 실행 하지 않습니다.  없음 입력 합니다 또는 마스터 구문에서 묵시적된 장애물이입니다.