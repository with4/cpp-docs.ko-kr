---
title: "컴파일러 오류 C3719 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3719"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3719"
ms.assetid: d0d59d4e-babb-4480-9ef7-70cf1a28165c
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3719
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'interface': 이벤트 소스에 기반한 인터페이스는 COM 이벤트에만 사용될 수 있습니다.  
  
 인터페이스를 비 COM 컨텍스트에 선언했습니다.  
  
 다음 샘플에서는 C3719 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3719a.cpp  
#define _ATL_ATTRIBUTES 1  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module(name="MyLibrary", version="1.2", helpfile="MyHelpFile")];  
  
[object]  
__interface I {  
   HRESULT func1();  
};  
  
[event_source(native), coclass]  
struct A {  
   __event __interface I;   // C3719  
  
   // try the following line instead  
   // __event func2();  
};  
  
int main() {  
}  
```  
  
 이 오류를 해결하려면 [object](../../windows/object-cpp.md), [coclass](../../windows/coclass.md), [event\_source](../../windows/event-source.md) 및 [event\_receiver](../../windows/event-receiver.md) 특성을 적절하게 적용하여 인터페이스 COM 클래스를 사용하고 있는 클래스를 만드십시오.  예를 들면 다음과 같습니다.  
  
```  
// C3719b.cpp  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
  
[module(name="xx")];  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface I {  
   HRESULT f();  
};  
  
[coclass, event_source(com) , uuid("00000000-0000-0000-0000-000000000002")]  
struct MyStruct {  
   __event __interface I;  
};  
  
[event_receiver(com)]  
struct MyStruct2 {  
   void f() {  
   }  
   MyStruct2(I* pB) {  
      __hook(&I::f, pB, &MyStruct2::f);  
   }  
};  
  
int main()  
{  
}  
```