---
title: "EXTERN (MASM) | Microsoft Docs"
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
  - "extern"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "EXTERN directive"
ms.assetid: 667d703d-3aaf-4139-a586-29bc5dab1aff
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# EXTERN (MASM)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

하나 이상의 외부 변수, 레이블 또는 호출 된 기호를 정의  *이름* 는 `type`.  
  
## 구문  
  
```  
  
   EXTERN [[langtype]] name [[(altid)]] :  
type [[, [[langtype]] name [[(altid)]] :type]]...  
```  
  
## 설명  
 `type` 수 있습니다  [ABS](../../assembler/masm/operator-abs.md), imports  *이름* 상수는.  다른 이름으로 동일한  [EXTRN](../../assembler/masm/extrn.md).  
  
## 참고 항목  
 [Directives Reference](../../assembler/masm/directives-reference.md)