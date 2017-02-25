---
title: "C 런타임 오류 R6032 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "R6032"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "R6032"
ms.assetid: 52092a63-cc51-444a-bfc3-fad965a3558e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# C 런타임 오류 R6032
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

로캘 정보를 저장할 공간이 부족합니다.  
  
 런타임에서는 로캘 구분 함수에 대한 호출을 처리할 수 있도록 각 스레드에 로캘 관련 정보를 유지합니다.  이 정보에 사용할 메모리를 할당하지 못한 경우 런타임의 기본 기능 중 다수가 이 정보에 의존하므로 런타임에서 처리를 진행할 수 없습니다.