---
title: "MxCsr | Microsoft Docs"
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
ms.assetid: 4f3c229d-0862-4733-acc7-9ed7a0b870ce
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# MxCsr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

레지스터 상태에는 MxCsr도 포함됩니다.  호출 규칙에서는 이 레지스터를 volatile 부분과 비volatile 부분으로 나눕니다.  volatile 부분은 6개의 상태 플래그인 MXCSR\[0:5\]로 구성되어 있고, 레지스터의 나머지 부분인 MXCSR\[6:15\]는 비volatile로 간주됩니다.  
  
 비volatile 부분은 프로그램 실행을 시작할 때 다음과 같은 표준 값으로 설정됩니다.  
  
```  
MXCSR[6]         : Denormals are zeros - 0  
MXCSR[7:12]      : Exception masks all 1's (all exceptions masked)  
MXCSR[13:14]   : Rounding  control - 0 (round to nearest)  
MXCSR[15]      : Flush to zero for masked underflow - 0 (off)  
```  
  
 MXCSR 내의 비volatile 필드를 수정하는 호출 수신자는 이를 호출자에 반환하기 전에 복원해야 합니다.  또한 이러한 필드를 수정한 호출자는 호출 수신자에 수정된 값을 전달하도록 승인되지 않은 한 호출 수신자를 호출하기 전에 이를 표준 값으로 복원해야 합니다.  
  
 제어 플래그의 비volatile 특성과 관련된 규칙에는 두 가지 예외가 있습니다.  
  
-   비volatile MxCsr 플래그를 수정하도록 문서화된 함수의 경우  
  
-   전체 프로그램 분석 등을 통해 이러한 규칙을 위반한 프로그램이 해당 규칙을 위반하지 않은 프로그램과 동일한 동작을 수행하거나 의미를 갖는 경우  
  
 함수의 설명에서 특별히 언급하지 않는 한 함수 경계 사이에서 MXCSR의 volatile 부분의 상태에 대해서는 어떠한 가정도 할 수 없습니다.  
  
## 참고 항목  
 [호출 규칙](../build/calling-convention.md)