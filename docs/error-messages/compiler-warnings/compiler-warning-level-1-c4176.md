---
title: "컴파일러 경고(수준 1) C4176 | Microsoft Docs"
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
  - "C4176"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4176"
ms.assetid: cfffb934-219a-4a63-9df6-ba54405bf766
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고(수준 1) C4176
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'subcomponent': \#pragma 구성 요소 브라우저의 하위 구성 요소를 알 수 없습니다.  
  
 **구성 요소** pragma에 잘못된 하위 구성 요소가 포함되어 있습니다. 특정 이름에 대한 참조를 제외하려면 이름 앞에 **참조** 옵션을 사용해야 합니다.  
  
## 예제  
  
```  
// C4176.cpp // compile with: /W1 /LD #pragma component(browser, off, i)  // C4176 #pragma component(browser, off, references, i) // ok  
```