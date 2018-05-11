---
title: 컴파일러 오류 C3743 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3743
dev_langs:
- C++
helpviewer_keywords:
- C3743
ms.assetid: 7ca9a76e-7b60-46d1-ab8b-18600cf1a306
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cc9a0bab67bb4fb15627dde42b1d538a0ecce9d5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3743"></a>컴파일러 오류 C3743
수만 후크/언 후크 할 전체 인터페이스 event_receiver의 'layout_dependent' 매개 변수 참인 경우  
  
 [__unhook](../../cpp/unhook.md) 함수에 전달 된 값에 따라 소요 되는 매개 변수 개수에 따라 다른는 `layout_dependent` 에서 매개 변수는 [event_receiver](../../windows/event-receiver.md) 클래스입니다.  
  
 다음 샘플에서는 C3743 오류가 생성 됩니다.  
  
```  
// C3743.cpp  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
[module(name="xx")];  
[object] __interface I { HRESULT f(); };  
  
[event_receiver(com, layout_dependent=true), coclass]  
struct R : I {  
        HRESULT f() {  
      return 0;  
   }  
        R() {  
   }  
  
   R(I* a) {  
      __hook(I, a, &R::f);   // C3743  
      // The following line resolves the error.  
      // __hook(I, a);  
   }  
};  
```