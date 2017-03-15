---
title: "컴파일러 오류 C3739 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3739"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3739"
ms.assetid: acffe894-08b8-4bf2-9249-9501e6e2bad3
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C3739
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class': event\_receiver의 'layout\_dependent' 매개 변수가 true인 경우에만 지원되는 구문입니다.  
  
 이벤트의 전체 인터페이스를 후크하려고 했지만 [event\_receiver](../../windows/event-receiver.md) 특성의 `layout_dependent`가 true가 아닙니다. 한 번에 하나의 이벤트만 후크해야 합니다.  
  
 다음 샘플에서는 C3739 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3739.cpp  
struct A  
{  
   __event void e();  
};  
  
// event_receiver is implied  
// [ event_receiver(layout_dependent=false)]  
  
// use the following line instead  
// [event_receiver(com, layout_dependent=true), coclass ]  
struct B  
{  
   void f();  
   B(A* a)  
   {  
      __hook(A, a, &B::f);   // C3739  
      // use the following line instead to hook a single event  
      // __hook(&A::e, a, &B::f);  
   }  
};  
  
int main()  
{  
}  
```