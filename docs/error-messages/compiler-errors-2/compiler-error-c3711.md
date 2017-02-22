---
title: "컴파일러 오류 C3711 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3711"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3711"
ms.assetid: 26d581cc-2153-4ee0-b814-a371184be3e1
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C3711
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'method': 관리되지 않는 이벤트 소스 메서드는 void 또는 정수 계열 형식을 반환해야 합니다.  
  
 void 또는 정수 계열 형식을 반환하지 않는 메서드를 이벤트 소스에 정의했습니다.  이 오류를 해결하려면 이벤트와 이벤트 처리기가 `void` 반환 형식이나 정수 계열 형식\(예: `int` 또는 `long`\)을 사용해야 합니다.  
  
 다음 샘플에서는 C3711 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3711.cpp  
#include <atlbase.h>  
#include <atlcom.h>  
#include <atlctl.h>  
  
[event_source(native)]  
class CEventSrc {  
public:  
   __event float event1();   // C3711  
   // try the following line instead  
   // __event int event1();  
   // also change the handler, below  
};  
  
[event_receiver(native)]  
class CEventRec {  
public:  
   float handler1() {         // change float to int  
      return 0.0;             // change 0.0 to 0  
   }  
   void HookEvents(CEventSrc* pSrc) {  
      __hook(CEventSrc::event1, pSrc, CEventRec::handler1);  
   }  
   void UnhookEvents(CEventSrc* pSrc) {  
      __unhook(CEventSrc::event1, pSrc, CEventRec::handler1);  
   }  
};  
  
int main() {  
}  
```