---
title: "ML Fatal Error A1011 | Microsoft Docs"
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
  - "A1011"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A1011"
ms.assetid: 7fbf092d-4189-4330-a884-dfa2268fc3dd
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ML Fatal Error A1011
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**지시문 제어 블록에 있어야 합니다.**  
  
 어셈블러 하나 예상 되는 높은 수준의 지시문을 발견 했습니다.  다음 지시문 중 하나가 있습니다.  
  
-   [.다른](../../assembler/masm/dot-else.md) 없이  [.IF](../../assembler/masm/dot-if.md)  
  
-   [.ENDIF](../../assembler/masm/dot-endif.md) 없이  [.IF](../../assembler/masm/dot-if.md)  
  
-   [.ENDW](../../assembler/masm/dot-endw.md) 없이  [.반면](../../assembler/masm/dot-while.md)  
  
-   [.UNTILCXZ](../../assembler/masm/dot-untilcxz.md) 없이  [.반복](../../assembler/masm/dot-repeat.md)  
  
-   [.계속](../../assembler/masm/dot-continue.md) 없이  [.WHILE](../../assembler/masm/dot-while.md) or [.반복](../../assembler/masm/dot-repeat.md)  
  
-   [.중단](../../assembler/masm/dot-break.md) 없이  [.WHILE](../../assembler/masm/dot-while.md) or [.반복](../../assembler/masm/dot-repeat.md)  
  
-   [.다른](../../assembler/masm/dot-else.md) 다음`.ELSE`  
  
## 참고 항목  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)