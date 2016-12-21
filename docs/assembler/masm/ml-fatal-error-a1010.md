---
title: "ML Fatal Error A1010 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "A1010"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A1010"
ms.assetid: 9e0b5241-67f4-4740-8701-3b2d2d1ad9e4
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ML Fatal Error A1010
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**일치 하지 않는 블록 중첩:**  
  
 블록 시작 하 여 일치 하는 끝 없는 또는 블록 끝에 일치 하는 시작 하는 없었습니다.  다음 중 하나 포함 될 수 있습니다.  
  
-   와 같은 높은 수준의 지시문  [.IF](../../assembler/masm/dot-if.md), [.반복](../../assembler/masm/dot-repeat.md), 또는  [.반면](../../assembler/masm/dot-while.md).  
  
-   어셈블리 조건부 지시문을 같은  [IF](../../assembler/masm/if-masm.md),  [반복](../../assembler/masm/repeat.md), 또는  **때**.  
  
-   구조체 또는 공용 구조체 정의 합니다.  
  
-   프로시저 정의 합니다.  
  
-   세그먼트 정의 합니다.  
  
-   A  [POPCONTEXT](../../assembler/masm/popcontext.md) 지시문입니다.  
  
-   어셈블리 조건부 지시문 등는  [ELSE](../../assembler/masm/else-masm.md),  [ELSEIF](../../assembler/masm/elseif-masm.md), 또는  **ENDIF**  하지 않고 일치 하는  [IF](../../assembler/masm/if-masm.md).  
  
## 참고 항목  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)