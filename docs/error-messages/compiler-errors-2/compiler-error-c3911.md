---
title: "컴파일러 오류 C3911 | Microsoft Docs"
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
  - "C3911"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3911"
ms.assetid: b786da59-0e99-479d-bc0d-551126e940f2
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3911
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'event\_accessor\_method': 함수의 형식이 'signature'이어야 합니다.  
  
 이벤트의 접근자 메서드를 올바르게 선언하지 않았습니다.  
  
 자세한 내용은 [이벤트](../../windows/event-cpp-component-extensions.md)를 참조하십시오.  
  
 다음 샘플에서는 C3911 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3911.cpp  
// compile with: /clr  
using namespace System;  
delegate void H(String^, int);  
  
ref class X {  
   event H^ E1 {  
      void add() {}   // C3911  
      // try the following line instead  
      // void add(H ^ h) {}  
  
      void remove(){}  
      // try the following line instead  
      // void remove(H ^ h) {}  
  
      void raise(){}  
      // try the following line instead  
      // void raise(String ^ s, int i) {}  
   };  
};  
```