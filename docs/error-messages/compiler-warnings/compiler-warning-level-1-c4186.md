---
title: "컴파일러 경고(수준 1) C4186 | Microsoft Docs"
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
  - "C4186"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4186"
ms.assetid: caf3f7d8-f305-426b-8d4e-2b96f5c269ea
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고(수준 1) C4186
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#import 특성 'attribute'에 count 인수가 필요합니다. 무시됩니다.  
  
 `#import` 특성의 인수 개수가 잘못되었습니다.  
  
## 예제  
  
```  
// C4186.cpp // compile with: /W1 /c #import "stdole2.tlb" no_namespace("abc") rename("a","b","c")  // C4186  
```  
  
 `no_namespace` 특성은 인수를 사용하지 않습니다.**rename** 특성은 두 개의 인수만 사용합니다.