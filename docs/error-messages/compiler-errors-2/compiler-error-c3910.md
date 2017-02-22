---
title: "컴파일러 오류 C3910 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3910"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3910"
ms.assetid: cfcbe620-b463-463b-95ea-2d60ad33ebb5
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C3910
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'event': 'method' 멤버를 정의해야 합니다.  
  
 이벤트를 정의했지만 지정된 필수 접근자 메서드가 포함되어 있지 않습니다.  
  
 자세한 내용은 [이벤트](../../windows/event-cpp-component-extensions.md)를 참조하십시오.  
  
 다음 샘플에서는 C3910 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3910.cpp  
// compile with: /clr /c  
delegate void H();  
ref class X {  
   event H^ E {  
      // uncomment the following lines  
      // void add(H^) {}  
      // void remove( H^ h ) {}  
      // void raise( ) {}  
   };   // C3910  
  
   event H^ E2; // OK data member  
};  
```