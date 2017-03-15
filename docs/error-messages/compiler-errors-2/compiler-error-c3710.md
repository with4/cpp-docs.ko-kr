---
title: "컴파일러 오류 C3710 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3710"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3710"
ms.assetid: 18bec009-5b6f-464a-a21e-5d58a6936504
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C3710
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function': \_\_hook\/\_\_unhook의 이벤트 처리기 지정 구문이 잘못되었습니다.  
  
 [\_\_hook](../../cpp/hook.md) 또는 [\_\_unhook](../../cpp/unhook.md)를 사용하여 이벤트 처리기를 지정하는 경우 처리기는 올바른 메서드여야 합니다.  
  
## 예제  
 다음 샘플에서는 C3710 경고가 발생하는 경우를 보여 줍니다.  
  
```  
// C3710.cpp  
// compile with: /link /opt:noref  
#include <atlbase.h>  
#include <atlcom.h>  
#include <atlctl.h>  
#include <stdio.h>  
  
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
        printf_s("Executing handler1().\n");  
    }  
  
    void HookEvents(CEventSrc* pSrc)   
    {  
        __hook(&CEventSrc::event1, pSrc, 0);   // C3710  
        // try the following line instead  
        // __hook(&CEventSrc::event1, pSrc, &CEventRec::handler1);  
    }  
  
    void UnhookEvents(CEventSrc* pSrc)  
    {  
        __unhook(&CEventSrc::event1, pSrc, &CEventRec::handler1);  
    }  
};  
  
int main()  
{  
    CEventSrc eventSrc;  
    CEventRec eventRec;  
    eventRec.HookEvents(&eventSrc);  
    eventSrc.event1();  
    eventRec.UnhookEvents(&eventSrc);  
}  
```