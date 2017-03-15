---
title: "컴파일러 오류 C3554 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3554"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3554"
ms.assetid: aede18d5-fefc-4da9-9b69-adfe90bfa742
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# 컴파일러 오류 C3554
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'decltype'을 다른 형식 지정자와 함께 사용할 수 없습니다.  
  
 형식 지정자로 `decltype()` 키워드를 한정할 수는 없습니다. 예를 들어 다음 코드 조각은 C3554 오류를 생성합니다.  
  
```  
int x; unsigned decltype(x); // C3554  
```