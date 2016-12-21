---
title: "컴파일러 경고 (수준 1) C4618 | Microsoft Docs"
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
  - "C4618"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4618"
ms.assetid: 6ff10d0a-6d5b-4373-8196-1d57bb6b1611
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4618
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

pragma 매개 변수에 빈 문자열이 있으므로 pragma가 무시됩니다.  
  
 **\#pragma**에 대한 인수로 null 문자열을 지정했습니다.  
  
 pragma가 인수 없이 처리되었습니다.  
  
 다음 샘플에서는 C4618 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4618.cpp  
// compile with: /W1 /LD  
#pragma code_seg("")   // C4618  
```