---
title: "컴파일러 오류 C3743 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3743"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3743"
ms.assetid: 7ca9a76e-7b60-46d1-ab8b-18600cf1a306
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C3743
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

event\_receiver의 'layout\_dependent' 매개 변수가 true인 경우에만 전체 인터페이스를 후크\/언후크할 수 있습니다.  
  
 [\_\_unhook](../../cpp/unhook.md) 함수는 [event\_receiver](../../windows/event-receiver.md) 클래스의 `layout_dependent` 매개 변수에 전달된 값에 따라 사용하는 매개 변수의 개수가 달라집니다.  
  
 다음 샘플에서는 C3743 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3743.cpp  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
[module(name="xx")];  
[object] __interface I { HRESULT f(); };  
  
[event_receiver(com, layout_dependent=true), coclass]  
struct R : I {  
        HRESULT f() {  
      return 0;  
   }  
        R() {  
   }  
  
   R(I* a) {  
      __hook(I, a, &R::f);   // C3743  
      // The following line resolves the error.  
      // __hook(I, a);  
   }  
};  
```