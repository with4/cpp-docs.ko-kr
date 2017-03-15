---
title: "컴파일러 오류 C3912 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3912"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3912"
ms.assetid: 674e050c-11fb-4db1-8bdf-a3e95b41161d
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C3912
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'event': 이벤트 형식이 대리자 형식이어야 합니다.  
  
 이벤트를 선언했지만 적절한 형식이 아닙니다.  
  
 자세한 내용은 [이벤트](../../windows/event-cpp-component-extensions.md)를 참조하십시오.  
  
 다음 샘플에서는 C3912 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3912.cpp  
// compile with: /clr  
delegate void H();  
ref class X {  
   event int Ev;   // C3912  
   event H^ Ev2;   // OK  
};  
```