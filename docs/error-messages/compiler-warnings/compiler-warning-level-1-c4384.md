---
title: "컴파일러 경고 (수준 1) C4384 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4384"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4384"
ms.assetid: fafa8eb2-cbfc-4edb-8b0f-511ff5d37ac0
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# 컴파일러 경고 (수준 1) C4384
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#pragma 'make\_public'은\(는\) 전역 범위에서만 사용할 수 있습니다.  
  
 [make\_public](../../preprocessor/make-public.md) pragma를 잘못 적용했습니다.  
  
## 예제  
 다음 샘플에서는 C4384 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4384.cpp  
// compile with: /c /W1  
namespace n {  
   #pragma make_public(N::C)   // C4384  
   namespace N {  
      class C {};  
   }  
}  
```