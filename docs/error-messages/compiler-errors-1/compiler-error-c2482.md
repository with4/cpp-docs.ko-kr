---
title: "컴파일러 오류 C2482 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2482"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2482"
ms.assetid: 98c87da2-625c-4cc2-9bf7-78d15921e779
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2482
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 'thread' 데이터를 동적으로 초기화할 수 없습니다.  
  
 `thread` 특성을 통해 선언된 변수는 런타임 계산이 필요한 식을 사용하여 초기화할 수 없습니다.  `thread` 데이터 초기화에는 정적 식이 필요합니다.  
  
 다음 샘플에서는 C2482 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2482.cpp  
// compile with: /c  
#define Thread __declspec( thread )  
Thread int tls_i = tls_i;   // C2482  
  
int j = j;   // OK in C++; C error  
Thread int tls_i = sizeof( tls_i );   // Okay in C and C++  
```