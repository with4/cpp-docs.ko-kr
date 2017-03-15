---
title: "컴파일러 오류 C3556 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3556"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3556"
ms.assetid: 9b002dcc-494e-414f-9587-20c2a0a39333
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 오류 C3556
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'expression': 'decltype'의 인수가 잘못되었습니다.  
  
 컴파일러가 `decltype(``expression``)` 형식 지정자의 인수인 식의 형식을 추론할 수 없습니다. 다음 코드 예제에서는 `myFunction`이 오버로드되어 컴파일러가 `myFunction` 인수의 형식을 추론할 수 없습니다.  
  
```  
void myFunction(); void myFunction(int); decltype(myFunction); // C3556  
```