---
title: "컴파일러 오류 C3703 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3703"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3703"
ms.assetid: 7e3677d9-f2be-4c26-998f-423564e9023c
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C3703
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'event handler': 이벤트 처리기 메서드는 소스 'event'과\(와\) 같은 저장소 클래스를 사용해야 합니다.  
  
 [event](../../cpp/event-handling.md)가 후크된 이벤트 처리기와는 다른 저장소 클래스를 사용합니다.  예를 들어, 이 오류는 이벤트 처리기가 정적 멤버 함수이고 이벤트는 정적이 아닌 경우에 발생합니다.  이 오류를 해결하려면 이벤트 및 이벤트 처리기에 동일한 저장소 클래스를 제공하십시오.  
  
 다음 샘플에서는 C3703 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3703.cpp  
// C3703 expected  
#include <stdio.h>  
  
[event_source(type=native)]  
class CEventSrc {  
public:  
   __event static void MyEvent();  
};  
  
[event_receiver(type=native)]  
class CEventHandler {  
public:  
   // delete the following line to resolve  
   void MyHandler() {}  
  
   // try the following line instead  
   // static void MyHandler() {}  
  
   void HookIt(CEventSrc* pSource) {  
      __hook(CEventSrc::MyEvent, pSource, &CEventHandler::MyHandler);  
   }  
  
   void UnhookIt(CEventSrc* pSource) {  
      __unhook(CEventSrc::MyEvent, pSource, &CEventHandler::MyHandler);  
   }  
};  
  
int main() {  
   CEventSrc src;  
   CEventHandler hnd;  
  
   hnd.HookIt(&src);  
   __raise src.MyEvent();  
   hnd.UnhookIt(&src);  
}  
```