---
title: "FpCsr | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: dff95d5d-7589-4432-82db-64b459c24352
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# FpCsr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

레지스터 상태에는 x87 FPU 제어 단어도 포함됩니다.  호출 규칙에 따라 이 레지스터는 비volatile로 설정됩니다.  
  
 x87 FPU 제어 단어 레지스터는 프로그램 실행을 시작할 때 다음과 같은 표준 값으로 설정됩니다.  
  
```  
FPCSR[0:6]: Exception masks all 1's (all exceptions masked)  
FPCSR[7]: Reserved – 0  
FPCSR[8:9]: Precision Control – 10B (double precision)  
FPCSR[10:11]: Rounding  control - 0 (round to nearest)  
FPCSR[12]: Infinity control – 0 (not used)  
```  
  
 FPCSR 내의 필드를 수정하는 호출 수신자는 이를 호출자에 반환하기 전에 복원해야 합니다.  또한 이러한 필드를 수정한 호출자는 호출 수신자에 수정된 값을 전달하도록 승인되지 않은 한 호출 수신자를 호출하기 전에 이를 표준 값으로 복원해야 합니다.  
  
 제어 플래그의 비volatile 특성과 관련된 규칙에는 두 가지 예외가 있습니다.  
  
1.  비volatile FpCsr 플래그를 수정하도록 문서화된 함수의 경우  
  
2.  전체 프로그램 분석 등을 통해 이러한 규칙을 위반한 프로그램이 해당 규칙을 위반하지 않은 프로그램과 동일한 동작을 수행하거나 의미를 갖는 경우  
  
## 참고 항목  
 [호출 규칙](../build/calling-convention.md)