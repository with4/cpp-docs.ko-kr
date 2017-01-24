---
title: "ML Fatal Error A1007 | Microsoft Docs"
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
  - "A1007"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A1007"
ms.assetid: bcf9c826-beb3-4e93-91fe-1ffd34995fbf
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ML Fatal Error A1007
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**너무 깊은 중첩 수준**  
  
 어셈블러는 중첩 한계에 도달 했습니다.  별도로 언급 하지 않는 20 수준 있습니다.  
  
 다음 중 하나 너무 많이 중첩 되었습니다.  
  
-   와 같은 높은 수준의 지시문  [.IF](../../assembler/masm/dot-if.md), [.반복](../../assembler/masm/dot-repeat.md), 또는  [.반면](../../assembler/masm/dot-while.md).  
  
-   구조체 정의 합니다.  
  
-   어셈블리 조건부 지시문입니다.  
  
-   프로시저 정의 합니다.  
  
-   A  [PUSHCONTEXT](../../assembler/masm/pushcontext.md) 지시문 \(10도 수\).  
  
-   세그먼트 정의 합니다.  
  
-   Include 파일입니다.  
  
-   매크로입니다.  
  
## 참고 항목  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)