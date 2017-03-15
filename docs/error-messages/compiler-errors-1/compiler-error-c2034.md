---
title: "컴파일러 오류 C2034 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2034"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2034"
ms.assetid: 953d70fa-bde9-4ce6-a55d-741e7bc63ff4
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C2034
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 비트 필드의 형식이 비트 수에 비해 너무 작습니다.  
  
 비트 필드 선언의 비트 수가 기본 형식의 크기를 초과합니다.  
  
 다음 샘플에서는 C2034 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2034.cpp  
struct A {  
   char test : 9;   // C2034, char has 8 bits  
};  
```  
  
 다음과 같이 해결할 수 있습니다.  
  
```  
// C2034b.cpp  
// compile with: /c  
struct A {  
   char test : 8;  
};  
```