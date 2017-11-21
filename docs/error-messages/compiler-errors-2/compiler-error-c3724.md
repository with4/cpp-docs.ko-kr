---
title: "컴파일러 오류 C3724 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3724
dev_langs: C++
helpviewer_keywords: C3724
ms.assetid: cab8aba7-14fc-406f-8cc6-32744c8f31c1
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ff6bbed7c54b3be98ed244b375ed05aca79c953f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3724"></a>컴파일러 오류 C3724
해야 #include \<. h >를 사용 하 여 이벤트에 다중 스레딩을 사용  
  
 Windows.h 파일은 사용 하는 경우 필요 이벤트에 다중 스레딩을 사용 합니다. 이 오류를 해결 하려면 추가 `#include <windows.h>` 수신기가 정의 이벤트 원본 및 이벤트에 있는 파일의 맨 위로 이동 합니다.  
  
```  
// C3724.cpp  
// uncomment the following line to resolve  
// #include <windows.h>  
  
[event_source(native), threading(apartment)]  
class CEventSrc {  
public:  
   __event void event1();   // C3724  
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