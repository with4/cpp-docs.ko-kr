---
title: "컴파일러 오류 C3717 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3717"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3717"
ms.assetid: ae4fceb1-2583-4577-b2f1-40971a017055
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C3717
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'method': 이벤트를 발생시키는 메서드를 정의할 수 없습니다.  
  
 구현 기능을 포함하는 이벤트 메서드를 선언했습니다.  [\_\_event](../../cpp/event.md) 메서드 선언에 정의를 포함할 수 없습니다.  이 오류를 해결하려면 이벤트 메서드 선언에 정의를 포함시키지 말아야 합니다.  예를 들어, 아래 코드에서 주석 처리된 부분의 지시대로 `event1` 선언에서 함수 본문을 제거하십시오.  
  
 다음 샘플에서는 C3717 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3717.cpp  
[event_source(native)]  
class CEventSrc {  
public:  
   __event void event1() {   // C3717  
   }  
  
   // remove definition for event1 and substitute following declaration  
   // __event void event1();  
};  
  
[event_receiver(native)]  
class CEventRec {  
public:  
   void handler1() {  
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