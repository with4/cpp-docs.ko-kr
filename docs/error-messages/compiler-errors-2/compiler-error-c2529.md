---
title: "컴파일러 오류 C2529 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2529"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2529"
ms.assetid: 73a99e55-b91e-488d-9b72-cc80faaeb436
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2529
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'name': 참조에 대한 참조가 잘못되었습니다.  
  
 포인터 구문을 사용하고 포인터에 대한 참조를 선언하면 이 오류를 수정할 수 있습니다.  
  
 다음 샘플에서는 C2529 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2529.cpp  
// compile with: /c  
int i;  
int &ri = i;  
int &(&rri) = ri;   // C2529  
```