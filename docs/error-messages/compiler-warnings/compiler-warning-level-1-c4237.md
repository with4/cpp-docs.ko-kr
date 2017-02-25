---
title: "컴파일러 경고 (수준 1) C4237 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4237"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4237"
ms.assetid: f2e86c4b-80d8-460e-9429-83c5f3f5d7ca
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 경고 (수준 1) C4237
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'keyword' 키워드는 아직 지원되지 않지만 나중에 사용할 수 있도록 예약되었습니다.  
  
 C\+\+ 사양의 키워드는 Visual C\+\+ 컴파일러에서 구현되지 않지만 이 키워드를 사용자 정의 기호로 사용할 수 없습니다.  
  
 다음 샘플에서는 C4237 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4237.cpp  
// compile with: /W1 /c  
int export;   // C4237  
```