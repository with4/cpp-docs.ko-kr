---
title: 컴파일러 오류 C3741 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3741
dev_langs:
- C++
helpviewer_keywords:
- C3741
ms.assetid: ed311315-cc32-49c9-97fa-01b293d81526
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 67c1bdb78a48571f58b59930615bc3251f3eeea5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3741"></a>컴파일러 오류 C3741
'class': coclass 이어야 합니다. 때 event_receiver의 'layout_dependent' 매개 변수 = true  
  
 때 `layout_dependent=true` 에 대 한 프로그램 [event_receiver](../../windows/event-receiver.md) 있어야 클래스, 다음 클래스는 [coclass](../../windows/coclass.md) 특성입니다.  
  
 다음 샘플에서는 C3741  
  
```  
// C3741.cpp  
// compile with: /c  
// C3741 expected  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
[module(name="xx")];  
  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface I{ HRESULT f(); };  
  
// Delete the following line to resolve.  
[ event_receiver(com, layout_dependent=true)]  
  
// class or struct must be declared with coclass  
// Uncomment the following line to resolve.  
// [ event_receiver(com, layout_dependent=true), coclass, uuid("00000000-0000-0000-0000-000000000002")]  
struct R : I {  
   HRESULT f(){ return 0; }  
   R(){}  
   R(I* a){ __hook(I, a); }  
};  
```