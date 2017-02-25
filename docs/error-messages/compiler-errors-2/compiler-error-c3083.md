---
title: "컴파일러 오류 C3083 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3083"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3083"
ms.assetid: 05ff791d-52bb-41eb-9511-3ef89d7f4710
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# 컴파일러 오류 C3083
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function': '::'의 왼쪽에 있는 기호는 형식이어야 합니다.  
  
 함수를 잘못 호출했습니다.  
  
## 예제  
 다음 샘플에서는 C3083 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3083.cpp  
// compile with: /c  
struct N {  
   ~N();  
};  
  
struct N1 {  
   ~N1();  
};  
  
N::N::~N() {}   // C3083  
N1::~N1() {}   // OK  
```