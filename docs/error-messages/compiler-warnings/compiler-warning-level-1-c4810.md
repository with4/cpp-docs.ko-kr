---
title: "컴파일러 경고(수준 1) C4810 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4810"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4810"
ms.assetid: 39e2cae0-9c1c-4ac1-aaa0-5f661d06085b
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고(수준 1) C4810
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

pragma pack\(show\)의 값 \=\= n  
  
 이 경고는 [pack](../../preprocessor/pack.md) pragma의 **표시** 옵션을 사용할 때 발생합니다.*n*은 현재 팩 값입니다.  
  
 예를 들어 다음 코드는 C4810 경고가 pack pragma에서 작동하는 방식을 보여 줍니다.  
  
```  
// C4810.cpp // compile with: /W1 /LD // C4810 expected #pragma pack(show) #pragma pack(4) #pragma pack(show)  
```