---
title: 컴파일러 오류 C3711 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3711
dev_langs:
- C++
helpviewer_keywords:
- C3711
ms.assetid: 26d581cc-2153-4ee0-b814-a371184be3e1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 682748a9db6ab4c74ed4b71b8548aba54fc1649b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33266502"
---
# <a name="compiler-error-c3711"></a>컴파일러 오류 C3711
'method': 관리 되지 않는 이벤트 소스 메서드는 void 또는 정수 계열 형식을 반환 해야 합니다  
  
 Void 반환 하지 않는 이벤트 소스 또는 정수 계열 형식에 메서드를 정의 합니다. 이 오류를 해결 하려면 이벤트와 이벤트 처리기의 반환 형식이 확인 `void` 또는과 같은 정수 계열 형식을 `int` 또는 `long`합니다.  
  
 다음 샘플에서는 C3711 오류가 생성 됩니다.  
  
```  
// C3711.cpp  
#include <atlbase.h>  
#include <atlcom.h>  
#include <atlctl.h>  
  
[event_source(native)]  
class CEventSrc {  
public:  
   __event float event1();   // C3711  
   // try the following line instead  
   // __event int event1();  
   // also change the handler, below  
};  
  
[event_receiver(native)]  
class CEventRec {  
public:  
   float handler1() {         // change float to int  
      return 0.0;             // change 0.0 to 0  
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