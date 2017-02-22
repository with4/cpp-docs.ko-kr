---
title: "컴파일러 오류 C3553 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3553"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3553"
ms.assetid: 7f84bf37-6419-4ad3-ab30-64266100b930
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# 컴파일러 오류 C3553
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

decltype에 형식이 아니라 식이 필요합니다.  
  
 `decltype()` 키워드는 형식 이름이 아니다를 인수로 식을 사용하도록 요구합니다. 예를 들어 다음 코드 조각의 마지막 문은 C3553 오류를 생성합니다.  
  
 `int x = 0;`  
  
 `decltype(x+1);`  
  
 `decltype(int); // C3553`