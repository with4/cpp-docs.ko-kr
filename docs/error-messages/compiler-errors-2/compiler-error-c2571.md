---
title: "컴파일러 오류 C2571 | Microsoft Docs"
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
  - "C2571"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2571"
ms.assetid: c6522616-dee9-4d7d-9bf8-30a7e1deaadf
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2571
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 가상 함수가 'union' 공용 구조체에 있을 수 없습니다.  
  
 공용 구조체에 가상 함수가 선언되었습니다.  가상 함수는 클래스나 구조체에만 선언할 수 있습니다.  다음과 같이 해결할 수 있습니다.  
  
1.  공용 구조체를 클래스나 구조체로 변경합니다.  
  
2.  함수를 비가상 함수로 만듭니다.  
  
 다음 샘플에서는 C2571 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2571.cpp  
// compile with: /c  
union A {  
   virtual void func1();   // C2571  
   void func2();   // OK  
};  
```