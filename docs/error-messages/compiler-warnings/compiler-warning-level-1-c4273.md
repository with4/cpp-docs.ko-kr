---
title: "컴파일러 경고 (수준 1) C4273 | Microsoft Docs"
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
  - "C4273"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4273"
ms.assetid: cc18611d-9454-40a4-ad73-69823d5888fb
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4273
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : dll 링크가 일치하지 않습니다.  
  
 한 파일에 있는 두 개의 정의에 [dllimport](../../cpp/dllexport-dllimport.md)를 서로 다르게 사용했습니다.  
  
## 예제  
 다음 샘플에서는 C4273 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4273.cpp  
// compile with: /W1 /c  
char __declspec(dllimport) c;  
char c;   // C4273, delete this line or the line above to resolve  
```  
  
## 예제  
 다음 샘플에서는 C4273 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4273_b.cpp  
// compile with: /W1 /clr /c  
#include <stdio.h>  
extern "C" int printf_s(const char *, ...);   // C4273  
```