---
title: "컴파일러 오류 C2046 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2046"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2046"
ms.assetid: f0c8f9dd-dbd7-4c4a-8838-fde54208ec71
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2046
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

대\/소문자가 잘못되었습니다.  
  
 `case` 키워드는 `switch` 문에만 나타날 수 있습니다.  
  
 다음 샘플에서는 C2046을 생성합니다.  
  
```  
// C2046.cpp int main() { case 0:   // C2046 }  
```  
  
 해결 방법:  
  
```  
// C2046b.cpp int main() { int i = 0; switch(i) { case 0: break; default: break; } }  
```