---
title: "컴파일러 경고 (수준 1) C4293 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4293"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4293"
ms.assetid: babecd96-eb51-41a5-9835-462c7a46dbad
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 1) C4293
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator' : 시프트 횟수가 음수이거나 너무 큽니다. 정의되지 않은 동작입니다.  
  
 시프트 횟수가 음수이거나 너무 크면 이미지 결과의 동작이 정의되지 않습니다.  
  
## 예제  
 다음 샘플에서는 C4293 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4293.cpp  
// compile with: /c /W1  
unsigned __int64 combine (unsigned lo, unsigned hi) {  
  
   return (hi << 32) | lo;   // C4293  
  
   // try the following line instead  
   // return ( (unsigned __int64)hi << 32) | lo;  
}  
```