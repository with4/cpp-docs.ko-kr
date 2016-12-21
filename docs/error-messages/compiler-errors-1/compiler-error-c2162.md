---
title: "컴파일러 오류 C2162 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2162"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2162"
ms.assetid: 34923628-d35e-48ab-9072-b95e3b5f6b45
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2162
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

매크로 형식 매개 변수가 필요합니다.  
  
 문자열화 연산자\(\#\) 다음에 오는 토큰이 형식 매개 변수 이름이 아닙니다.  
  
## 예제  
 다음 샘플에서는 C2162 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2162.cpp  
// compile with: /c  
#include <stdio.h>  
  
#define print(a) printf_s(b)   // OK  
#define print(a) printf_s(#b)    // C2162  
```