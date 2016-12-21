---
title: "컴파일러 오류 C3713 | Microsoft Docs"
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
  - "C3713"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3713"
ms.assetid: 75c6b9b6-955b-49bd-9bc8-ced88b496a1f
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3713
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'method': 이벤트 처리기 메서드는 'method' 소스와 같은 함수 매개 변수를 사용해야 합니다.  
  
 소스 이벤트 메서드와 동일한 매개 변수를 사용하지 않는 이벤트 처리기 메서드를 정의했습니다.  이 오류를 해결하려면 이벤트 처리기 메서드에 소스 이벤트 메서드와 동일한 매개 변수를 제공하십시오.  
  
 다음 샘플에서는 C3713 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3713.cpp  
// compile with: /c  
[event_source(native)]  
class CEventSrc {  
public:  
   __event void event1(int nValue);  
   // try the following line instead  
   // __event void event1();  
};  
  
[event_receiver(native)]  
class CEventRec {  
public:  
   void handler1() {}  
  
   void HookEvents(CEventSrc* pSrc) {  
      __hook(&CEventSrc::event1, pSrc, &CEventRec::handler1);   // C3713  
   }  
  
   void UnhookEvents(CEventSrc* pSrc) {  
      __unhook(&CEventSrc::event1, pSrc, &CEventRec::handler1); // C3713  
   }  
};  
```