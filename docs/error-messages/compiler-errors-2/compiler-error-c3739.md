---
title: 컴파일러 오류 C3739 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3739
dev_langs:
- C++
helpviewer_keywords:
- C3739
ms.assetid: acffe894-08b8-4bf2-9249-9501e6e2bad3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 283156f436695c011642dc2603d2cc846a449b3a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3739"></a>컴파일러 오류 C3739
'class': event_receiver의 'layout_dependent' 매개 변수 참인 경우에 구문을 사용할  
  
 전체 이벤트 인터페이스를 연결 하려고 하지만 `layout_dependent` 에 [event_receiver](../../windows/event-receiver.md) 특성이 true; 한 번에 하나의 이벤트를 연결 해야 합니다.  
  
 다음 샘플에서는 C3739 오류가 생성 됩니다.  
  
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