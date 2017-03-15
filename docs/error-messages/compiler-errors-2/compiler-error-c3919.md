---
title: "컴파일러 오류 C3919 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3919"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3919"
ms.assetid: 5f8eddda-d751-478b-930d-e18f7191ddfb
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C3919
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'event\_method': 함수의 형식이 'type'이어야 합니다.  
  
 이벤트 접근자 메서드를 올바르게 선언하지 않았습니다.  
  
 이벤트에 대한 자세한 내용은 [이벤트](../../windows/event-cpp-component-extensions.md)를 참조하십시오.  
  
 다음 샘플에서는 C3919 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3919.cpp  
// compile with: /clr /c  
using namespace System;  
delegate void D(String^);  
ref class R {  
   event D^ e {  
      int add(int);   // C3919  
      int remove(int);   // C3919  
  
      void add(D^);   // OK  
      void remove(D^);   // OK  
   }  
};  
```