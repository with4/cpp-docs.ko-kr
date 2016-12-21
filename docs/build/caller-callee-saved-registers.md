---
title: "호출자/호출 수신자 저장 레지스터 | Microsoft Docs"
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
ms.assetid: 0533bd4b-d6bb-4ce1-8201-495e16870cbb
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 호출자/호출 수신자 저장 레지스터
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

RAX, RCX, RDX, R8, R9, R10, R11 레지스터는 volatile로 간주되고, 전체 프로그램 최적화 같은 분석에 의해 안전성이 증명될 수 없는 한 함수를 호출할 때 소멸되는 것으로 취급해야 합니다.  
  
 RBX, RBP, RDI, RSI, RSP, R12, R13, R14 및 R15 레지스터는 비volatile로 간주되고, 이들 레지스터를 사용하는 함수에서 저장하고 복원해야 합니다.  
  
## 참고 항목  
 [호출 규칙](../build/calling-convention.md)