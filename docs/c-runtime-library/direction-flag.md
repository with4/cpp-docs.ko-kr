---
title: "방향 플래그 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.flags"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "방향 플래그"
ms.assetid: 0836b4af-dbbb-4ab8-a4b2-156f2e2099e2
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 방향 플래그
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

방향 플래그는 인텔 80x86에 프로세서에 특정 CPU 플래그입니다.  MOVS, MOVSD, MOVSW 등과 같은 REP \(반복\) 접두사를 사용 하는 모든 어셈블리 명령에 적용 됩니다.  적용 가능한 명령에 제공 되는 주소는 방향 플래그가 해제 되면 증가합니다.  
  
 C 런타임 루틴은 방향 플래그가 명백하다고 가정합니다.  C 런타임 함수를 사용 하여 다른 함수를 사용할 경우 다른 함수가 방향 플래그를 내버려 두거나 원래 상태로 복원되도록 할 수 있도록 해야 합니다.  방향 플래그가 항목에 따라 명확하게 기대하는 것은 런타임 코드를보다 빠르고 효율적으로 만드는 것입니다.  
  
 이러한 문자열 조작 및 버퍼 조작 루틴과 C 런타임 라이브러리 함수는 방향 플래그가 분명히 있을 것으로 예상합니다.  
  
## 참고 항목  
 [CRT 라이브러리 기능](../c-runtime-library/crt-library-features.md)