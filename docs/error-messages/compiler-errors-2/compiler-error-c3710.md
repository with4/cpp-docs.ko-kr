---
title: "컴파일러 오류 C3710 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3710
dev_langs:
- C++
helpviewer_keywords:
- C3710
ms.assetid: 18bec009-5b6f-464a-a21e-5d58a6936504
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 32c6b54339256680fad147ed33d0bc641fb8481f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3710"></a>컴파일러 오류 C3710
'function': __hook의 이벤트 처리기 지정 구문이 잘못 /\__unhook  
  
 와 이벤트 처리기를 지정 하는 경우 [__hook](../../cpp/hook.md) 또는 [__unhook](../../cpp/unhook.md), 처리기 올바른 메서드가 이어야 합니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C3710  
  
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