---
title: "컴파일러 오류 C3886 | Microsoft Docs"
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
  - "C3886"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3886"
ms.assetid: 485f6c12-cc1b-4146-9034-409a0a5e615e
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3886
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var' : 리터럴 데이터 멤버는 초기화되어야 합니다.  
  
 [리터럴](../../windows/literal-cpp-component-extensions.md) 변수를 선언할 때 이를 초기화해야 합니다.  
  
 다음 샘플에서는 C3886 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3886.cpp  
// compile with: /clr /c  
ref struct Y1 {  
   literal int staticConst;   // C3886  
   literal int staticConst2 = 0;   // OK  
};  
```