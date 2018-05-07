---
title: 컴파일러 오류 C3703 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3703
dev_langs:
- C++
helpviewer_keywords:
- C3703
ms.assetid: 7e3677d9-f2be-4c26-998f-423564e9023c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 344554875e771a1a5c3412613fd77307651a5c7d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3703"></a>컴파일러 오류 C3703
'이벤트 처리기': 이벤트 처리기 메서드는 'event' 소스로 같은 저장소 클래스 있어야  
  
 [이벤트](../../cpp/event-handling.md) 가 연결 되어 있는 이벤트 처리기는 다른 저장소 클래스입니다. 예를 들어이 오류는 이벤트 처리기는 정적 멤버 함수는 이벤트가 고정 되지 않습니다. 경우에 발생 합니다. 이 오류를 해결 하려면 이벤트 및 이벤트 처리기에 동일한 저장소 클래스를 제공 합니다.  
  
 다음 샘플에서는 C3703 오류가 생성 됩니다.  
  
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