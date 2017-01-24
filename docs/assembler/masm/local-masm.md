---
title: "LOCAL (MASM) | Microsoft Docs"
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
  - "Local"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LOCAL directive"
ms.assetid: 76147e2d-23ca-4f1e-8817-81428becd113
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# LOCAL (MASM)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

첫 번째 지시문을 매크로 내에서  **로컬** 매크로의 각 인스턴스에 고유한 레이블을 정의 합니다.  
  
## 구문  
  
```  
  
      LOCAL localname [[, localname]]...  
LOCAL label [[ [count ] ]] [[:type]] [[, label [[ [count] ]] [[type]]]]...  
```  
  
## 설명  
 프로시저 정의에서 두 번째 지시문 \(**PROC**\),  **로컬** 절차 기간 동안 존재 하는 스택 기반 변수를 만듭니다.  *레이블* 단순 변수 또는 포함 하는 배열이 될 수 있습니다  *수* 요소입니다.  
  
## 참고 항목  
 [Directives Reference](../../assembler/masm/directives-reference.md)