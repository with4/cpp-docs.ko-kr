---
title: ".IF | Microsoft Docs"
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
  - ".IF"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".IF directive"
ms.assetid: dccc7615-8fc7-4829-9f39-0ee405f6c1e3
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# .IF
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

테스트 하는 코드를 생성 `condition1` \(AX, 예를 들어, \> 7\) 및 실행은  *문* 은 이 조건이 만족 되는 경우.  
  
## 구문  
  
```  
  
   .IF condition1   
statements  
[[.ELSEIF condition2   
   statements]]  
[[.ELSE  
   statements]]  
.ENDIF  
```  
  
## 설명  
 If a [.다른](../../assembler/masm/dot-else.md) 원래 조건이 false 이면 다음 문을 실행 합니다.  참고 조건을 런타임 시 계산 되는.  
  
## 참고 항목  
 [Directives Reference](../../assembler/masm/directives-reference.md)