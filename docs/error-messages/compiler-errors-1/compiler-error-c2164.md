---
title: "컴파일러 오류 C2164 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2164"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2164"
ms.assetid: 55df5024-68a8-45a8-ae6c-e6dba35318a2
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# 컴파일러 오류 C2164
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 내장 함수를 선언하지 않았습니다.  
  
 `intrinsic` pragma가 선언되지 않은 함수를 사용합니다\(**\/Oi**에서만 발생\).  또는 컴파일러 내장 pragma 중 하나가 헤더 파일 없이 사용되었습니다.  
  
 다음 샘플에서는 C2164 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2164.c  
// compile with: /c  
// processor: x86  
// Uncomment the following line to resolve.  
// #include "xmmintrin.h"  
void b(float *p) {  
   _mm_load_ss(p);   // C2164  
}  
```