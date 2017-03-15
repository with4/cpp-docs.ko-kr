---
title: "이전 코드를 위한 부동 소수점 지원(Visual C++) | Microsoft Docs"
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
ms.assetid: a2a26b96-7bc2-418a-981a-51aa1a0294a2
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 이전 코드를 위한 부동 소수점 지원(Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MMX와 부동 소수점 스택 레지스터\(MM0\-MM7\/ST0\-ST7\)는 컨텍스트를 전환해도 유지됩니다.  이러한 레지스터에 대한 명시적인 호출 규칙은 없습니다.  이러한 레지스터는 커널 모드 코드에서만 사용하도록 엄격하게 제한되어 있습니다.  
  
## 참고 항목  
 [호출 규칙](../build/calling-convention.md)