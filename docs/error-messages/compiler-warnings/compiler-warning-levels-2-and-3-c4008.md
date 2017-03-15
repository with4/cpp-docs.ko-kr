---
title: "컴파일러 경고(수준 2 및 3) C4008 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4008"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4008"
ms.assetid: fb45e535-cb68-4743-80e9-a6e34cfffeca
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 경고(수준 2 및 3) C4008
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier': 'attribute' 특성이 무시됩니다.  
  
 컴파일러가 함수\(수준 3 경고\) 또는 데이터\(수준 2 경고\)에 대한 `__fastcall`, **static** 또는 **inline** 특성을 무시했습니다.  
  
### 다음과 같은 가능한 원인을 확인하여 수정하려면  
  
1.  데이터가 있는 `__fastcall` 특성  
  
2.  **main** 함수가 있는 **static** 또는 **inline** 특성