---
title: 컴파일러 오류 C3712 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3712
dev_langs:
- C++
helpviewer_keywords:
- C3712
ms.assetid: 65b1fcaf-be89-4c55-9e40-25ec03457253
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: df27d74f276f70cb93a7e862e452b3a6d0eb4e55
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33277165"
---
# <a name="compiler-error-c3712"></a>컴파일러 오류 C3712
'method': 이벤트 처리기 메서드는 소스와 같은 형식 'method' 반환 해야 합니다  
  
 소스 이벤트 메서드와 동일한 형식이 반환 하지 않는 이벤트 처리기 메서드를 정의 합니다. 이 오류를 해결 하려면 이벤트 처리기 메서드를 소스 이벤트 메서드의 것과 동일한 반환 형식을 제공 합니다.  
  
 다음 샘플에서는 C3712 오류가 생성 됩니다.  
  
```  
// C3712.cpp  
// compile with: /c  
[event_source(native)]  
class CEventSrc {  
public:  
   __event void event1();  
};  
  
[event_receiver(native)]  
class CEventRec {  
public:  
   int handler1() { return 0; }  
   // try the following line instead  
   // void handler1() {}  
  
   void HookEvents(CEventSrc* pSrc) {  
      __hook(&CEventSrc::event1, pSrc, &CEventRec::handler1);   // C3712  
   }  
   void UnhookEvents(CEventSrc* pSrc) {  
      __unhook(&CEventSrc::event1, pSrc, &CEventRec::handler1);   // C3712  
   }  
};  
```