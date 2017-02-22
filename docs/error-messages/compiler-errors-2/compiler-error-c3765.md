---
title: "컴파일러 오류 C3765 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3765"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3765"
ms.assetid: feadee7a-fcfb-402c-af2f-0e656f814a13
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C3765
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'event': event\_receiver로 표시된 클래스\/구조체 'type'에 이벤트를 정의할 수 없습니다.  
  
 [event\_receiver](../../windows/event-receiver.md) 특성으로 표시된 클래스는 [\_\_event](../../cpp/event.md) 선언을 포함할 수 없습니다.  
  
 다음 샘플에서는 C3765 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3765.cpp  
[event_receiver(native)]  
struct ER2 {  
   __event void f();   // C3765  
   __event void b(int);   // C3765  
};  
```