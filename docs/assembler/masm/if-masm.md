---
title: "IF (MASM) | Microsoft Docs"
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
  - "if"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IF directive"
ms.assetid: 82e43712-4f0c-4bf6-90ce-0663e81af707
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# IF (MASM)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

어셈블리의 부여  *ifstatements* 경우  *식 1* 입니다 true \(0이 아닌 값\) 또는  *elseifstatements* 경우  *식 1* false입니다 \(0\)와  *식 2* 마찬가지입니다.  
  
## 구문  
  
```  
  
   IF expression1  
ifstatements  
[[ELSEIF expression2  
   elseifstatements]]  
[[ELSE  
   elsestatements]]  
ENDIF  
```  
  
## 설명  
 다음 지시문을 대신 사용할 수 있습니다  [ELSEIF](../../assembler/masm/elseif-masm.md):  **ELSEIFB**,  **ELSEIFDEF**,  **ELSEIFDIF**,  **ELSEIFDIFI**,  **ELSEIFE**,  **ELSEIFIDN**,  **ELSEIFIDNI**,  **ELSEIFNB**, 및  **ELSEIFNDEF**.  선택적으로 어셈블리  *elsestatements* 이전 식이 false 인 경우.  참고 식 어셈블리 시간에 계산 되는.  
  
## 참고 항목  
 [Directives Reference](../../assembler/masm/directives-reference.md)