---
title: "INVOKE | Microsoft Docs"
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
  - "Invoke"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "INVOKE directive"
ms.assetid: 12d9bb40-33b9-411e-b801-45a1d675967e
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# INVOKE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

주어진 주소에 있는 프로시저를 호출  *식*, 스택 또는 레지스터 언어 형식의 표준 호출 규칙에 따라 해당 인수를 전달 합니다.  
  
## 구문  
  
```  
  
INVOKE   
expression [[, arguments]]  
```  
  
## 설명  
 프로시저에 전달 된 각 인수는 식, 레지스터 쌍을 또는 주소 식을 수 있습니다 \(식 앞에 의해 `ADDR`\).  
  
## 참고 항목  
 [Directives Reference](../../assembler/masm/directives-reference.md)