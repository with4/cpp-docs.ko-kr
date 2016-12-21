---
title: "컴파일러 경고 (수준 1) C4083 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4083"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4083"
ms.assetid: e7d3344e-5645-4d56-8460-d1acc9145ada
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4083
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'token'이\(가\) 있어야 하는데 'identifier' 식별자가 있습니다.  
  
 식별자가 **\#pragma** 문의 잘못된 위치에 있습니다.  
  
## 예제  
  
```  
// C4083.cpp  
// compile with: /W1 /LD  
#pragma warning disable:4083    // C4083  
#pragma warning(disable:4083)   //correct  
```  
  
 [\#pragma](../../preprocessor/pragma-directives-and-the-pragma-keyword.md) 지시문의 구문을 확인하십시오.