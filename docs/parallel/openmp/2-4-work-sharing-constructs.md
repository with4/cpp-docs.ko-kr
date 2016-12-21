---
title: "2.4 Work-sharing Constructs | Microsoft Docs"
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
ms.assetid: 25bb4ded-8466-4daa-a863-766b5a99b995
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.4 Work-sharing Constructs
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

작업 공유 생성자만 팀 구성원 사이에서 연결 된 문 실행 한 후 배포 합니다.  작업 공유 지시문 새 스레드를 시작 하지 않은 고 작업 공유 생성자 시작 부분에서 묵시적된 없음 장애물입니다.  
  
 작업 공유의 시퀀스를 생성 하 고  **장벽** 지시문을 발견 하는 팀의 모든 스레드를 동일 해야 합니다.  
  
 OpenMP 다음 작업 공유 생성자 정의 하 고 이러한 단원에서 설명 합니다.  
  
-   **에 대 한** 지시문  
  
-   **구역** 지시문  
  
-   **단일** 지시문