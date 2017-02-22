---
title: "컴파일러 경고 (수준 1) C4229 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4229"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4229"
ms.assetid: aadfc83b-1e5f-4229-bd0a-9c10a5d13182
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 경고 (수준 1) C4229
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

오래된 구문을 사용했습니다 : 데이터의 한정자가 무시됩니다.  
  
 `__cdecl`과 같은 Microsoft 한정자를 데이터 선언에 사용하는 것은 오래된 방법입니다.  
  
## 예제  
  
```  
// C4229.cpp  
// compile with: /W1 /LD  
int __cdecl counter;   // C4229 cdecl ignored  
```