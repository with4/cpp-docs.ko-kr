---
title: "컴파일러 오류 C2007 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2007"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2007"
ms.assetid: ecd09d99-5036-408b-9e46-bc15488f049e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C2007
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#define 구문  
  
 `#define` 다음에 식별자가 표시되지 않습니다.  이 오류를 해결하려면 식별자를 사용하십시오.  
  
 다음 샘플에서는 C2007 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2007.cpp  
#define   // C2007  
```  
  
 다음과 같이 해결할 수 있습니다.  
  
```  
// C2007b.cpp  
// compile with: /c  
#define true 1  
```