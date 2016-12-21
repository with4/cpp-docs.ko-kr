---
title: "컴파일러 오류 C3709 | Microsoft Docs"
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
  - "C3709"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3709"
ms.assetid: d5576b04-2f93-420a-8f3e-8b8e987e8dab
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3709
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function': \_\_hook\/\_\_unhook의 이벤트 지정 구문이 잘못되었습니다.  
  
 [\_\_hook](../../cpp/hook.md) 또는 [\_\_unhook](../../cpp/unhook.md)를 사용하여 이벤트 소스를 지정하는 경우 첫째 매개 변수는 올바른 이벤트 메서드이고 둘째 매개 변수는 올바른 이벤트 소스 개체\(메서드가 아님\)여야 합니다.  
  
 다음 샘플에서는 C3709 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3709.cpp  
// compile with: /LD  
[event_source(native)]  
class CEventSrc  
{  
public:  
   __event void event1();  
};  
  
[event_receiver(native)]  
class CEventRec  
{  
public:  
   void handler1()  
   {  
   }  
  
   void HookEvents(CEventSrc* pSrc)  
   {  
      __hook(bad, pSrc, CEventRec::handler1);   // C3709  
      // Try the following line instead:  
      // __hook(&CEventSrc::event1, pSrc, CEventRec::handler1);  
   }  
  
   void UnhookEvents(CEventSrc* pSrc)  
   {  
      __unhook(&CEventSrc::event1, pSrc, CEventRec::handler1);  
   }  
};  
```