---
title: "컴파일러 경고(수준 1) C4185 | Microsoft Docs"
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
  - "C4185"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4185"
ms.assetid: 37e7063a-35b1-4e05-ae31-e811dced02b9
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고(수준 1) C4185
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

알 수 없는 \#import 특성 'attribute'를 무시합니다.  
  
 attribute는 `#import`의 유효한 특성이 아닙니다. 무시됩니다.  
  
## 예제  
  
```  
// C4185.cpp // compile with: /W1 /c #import "stdole2.tlb" no_such_attribute   // C4185  
```