---
title: "GOTO (MASM) | Microsoft Docs"
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
  - "goto"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GOTO directive"
ms.assetid: 6a5f73e7-6784-4eae-ac52-4fc77a7f369f
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# GOTO (MASM)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

어셈블리가 표시 된 줄으로 이동 : **:***macrolabel*.  
  
## 구문  
  
```  
  
GOTO   
macrolabel  
  
```  
  
## 설명  
 **GOTO** 내부 에서만 사용할 수 있습니다  [매크로](../../assembler/masm/macro.md),  [에 대 한](../../assembler/masm/for-masm.md),  [FORC](../../assembler/masm/forc.md),  [반복](../../assembler/masm/repeat.md), 및  **때** 블록입니다.  레이블 줄에 지시문의 뿐 하 고 선행 콜론으로 시작 해야 합니다.  
  
## 참고 항목  
 [Directives Reference](../../assembler/masm/directives-reference.md)