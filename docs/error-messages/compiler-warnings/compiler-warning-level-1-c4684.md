---
title: "컴파일러 경고 (수준 1) C4684 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4684"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4684"
ms.assetid: e95f1a83-2784-4b05-ae94-12148e056e26
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 경고 (수준 1) C4684
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

특성으로 인해 잘못된 코드가 생성될 수 있습니다. 주의하여 사용하십시오.  
  
 일반적으로 사용할 수 없는 특성을 사용했습니다.  
  
 다음 샘플에서는 C4684 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4684.cpp  
// compile with: /W1 /LD  
 [module(name="xx")]; // C4684 expected  
[no_injected_text];  
```