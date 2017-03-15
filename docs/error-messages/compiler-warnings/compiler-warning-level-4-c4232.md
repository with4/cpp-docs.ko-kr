---
title: "컴파일러 경고 (수준 4) C4232 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4232"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4232"
ms.assetid: f92028a5-4ddd-43c1-97f5-4f724e5e14af
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 4) C4232
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

비표준 확장이 사용됨 : 'identifier' : dllimport 'dllimport'의 주소가 정적이 아닙니다. ID가 보장되지 않습니다.  
  
 Microsoft 확장\(\/Ze\)에서는 **dllimport** 한정자를 사용하여 선언한 함수의 주소로 비정적 값을 지정할 수 있지만  ANSI 규격\([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\)에서는 오류가 발생합니다.  
  
 다음 샘플에서는 C4232 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4232.c  
// compile with: /W4 /Ze /c  
int __declspec(dllimport) f();  
int (*pfunc)() = &f;   // C4232  
```