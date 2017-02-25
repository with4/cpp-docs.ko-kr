---
title: "컴파일러 경고 (수준 1) C4224 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4224"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4224"
ms.assetid: 1531cae0-5040-49fd-b149-005bb5085391
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 1) C4224
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

비표준 확장이 사용됨 : 'identifier' 정식 매개 변수가 이전에 형식으로 정의되었습니다.  
  
 이 식별자는 이전에 `typedef`로 사용했으므로  ANSI 규격\([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\)에서 경고가 발생합니다.  
  
## 예제  
  
```  
// C4224.cpp  
// compile with: /Za /W1 /LD  
typedef int I;  
void func ( int I );  // C4224  
```