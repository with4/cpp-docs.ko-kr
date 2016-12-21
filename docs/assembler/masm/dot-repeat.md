---
title: ".REPEAT | Microsoft Docs"
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
  - ".REPEAT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".REPEAT directive"
ms.assetid: cb8ad8c6-587b-42f9-a0ad-b5316a24918c
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# .REPEAT
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

반복 블록의 실행 코드를 생성  *문* 은 때까지 `condition` true가 됩니다.  [.UNTILCXZ](../../assembler/masm/dot-untilcxz.md), CX 0이 경우는 true가 될 수 있습니다 수 대체에 대 한  [.때까지](../../assembler/masm/dot-until.md).  `condition` 와 선택적입니다  **.UNTILCXZ**.  
  
## 구문  
  
```  
  
   .REPEAT  
statements  
.UNTIL condition  
```  
  
## 참고 항목  
 [Directives Reference](../../assembler/masm/directives-reference.md)