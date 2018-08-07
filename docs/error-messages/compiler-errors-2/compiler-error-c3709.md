---
title: 컴파일러 오류 C3709 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3709
dev_langs:
- C++
helpviewer_keywords:
- C3709
ms.assetid: d5576b04-2f93-420a-8f3e-8b8e987e8dab
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e42cb78c54dd1529a02733b5d8e0246ab6806289
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33263874"
---
# <a name="compiler-error-c3709"></a>컴파일러 오류 C3709
'function': __hook의 이벤트 지정 구문이 잘못 /\__unhook  
  
 이벤트 소스를 지정 하는 경우 [__hook](../../cpp/hook.md) 또는 [__unhook](../../cpp/unhook.md), 첫 번째 매개 변수 메서드여야 유효한 이벤트 및 두 번째 매개 변수는 올바른 이벤트 소스 개체 (메서드 아님) 이어야 합니다.  
  
 다음 샘플에서는 C3709 오류가 생성 됩니다.  
  
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