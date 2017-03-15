---
title: "컴파일러 경고 (수준 1) C4215 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4215"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4215"
ms.assetid: f2aab64d-1bab-4f75-95ee-89e1263047b1
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 1) C4215
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

비표준 확장을 사용했습니다 : long float입니다.  
  
 기본 Microsoft 확장\(\/Ze\)에서는 **long float**을 **double**로 처리하지만  그러나, ANSI 규격\([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\)에서는 다르게 간주합니다.  **double**을 사용하여 호환성을 유지하십시오.  
  
 다음 샘플에서는 C4215 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4215.cpp  
// compile with: /W1 /LD  
long float a;   // C4215  
  
// use the line below to resolve the warning  
// double a;  
```