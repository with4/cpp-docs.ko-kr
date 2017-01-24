---
title: "컴파일러 경고(수준 1) C4612 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4612"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4612"
ms.assetid: 21ac02b2-51cd-4aff-9b70-d543511d5962
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고(수준 1) C4612
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

포함 파일 이름에 오류가 있습니다.  
  
 파일 이름이 잘못되었거나 누락된 경우 **\#pragma include\_alias**에서 이 경고가 발생합니다.  
  
 **\#pragma include\_alias** 문에 대한 인수는 \(**"***파일 이름***"**\)으로부터의 인용 또는 꺾쇠 괄호 양식\(**\<***파일 이름***\>**\)을 사용할 수 있지만 둘 다 동일한 양식을 사용해야 합니다.  
  
## 예제  
  
```  
// C4612.cpp // compile with: /W1 /LD #pragma include_alias("StandardIO", <stdio.h>) // C4612  
```