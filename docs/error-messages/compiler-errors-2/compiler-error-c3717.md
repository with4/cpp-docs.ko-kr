---
title: "컴파일러 오류 C3717 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3717
dev_langs:
- C++
helpviewer_keywords:
- C3717
ms.assetid: ae4fceb1-2583-4577-b2f1-40971a017055
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8d3172709982106f34a7fec1830594d653b2c0e8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3717"></a>컴파일러 오류 C3717
'method': 이벤트를 발생 시키는 메서드를 정의할 수 없습니다  
  
 구현을 포함 하는 이벤트 메서드를 선언 했습니다. [__event](../../cpp/event.md) 메서드 선언에는 정의 사용할 수 없습니다. 이 오류를 해결 하려면 이벤트 메서드 선언 정의 있는지를 확인 합니다. 예를 들어 아래 코드에서 함수 본문을 제거는 `event1` 는 주석으로 표시 된 대로 선언 합니다.  
  
 다음 샘플에서는 C3717 오류가 생성 됩니다.  
  
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