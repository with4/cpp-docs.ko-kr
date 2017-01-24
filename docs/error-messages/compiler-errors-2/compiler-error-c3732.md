---
title: "컴파일러 오류 C3732 | Microsoft Docs"
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
  - "C3732"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3732"
ms.assetid: 2d55a7e1-9c39-4379-a093-2f7beb27e2ca
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3732
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'interface': COM 이벤트를 발생시키는 사용자 지정 인터페이스는 IDispatch에서 상속할 수 없습니다.  
  
 COM 이벤트를 지원하는 인터페이스는 `IDispatch`에서 상속할 수 없습니다.  자세한 내용은 [COM에서 이벤트 처리](../../cpp/event-handling-in-com.md)를 참조하십시오.  
  
 다음 오류는 C3732를 발생시킵니다.  
  
```  
// C3732.cpp  
#define _ATL_ATTRIBUTES 1  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module(name="test")];  
  
// to resolve this C3732, use dual instead of object  
// or inherit from IUnknown  
[ object ]  
__interface I : IDispatch  
{  
};  
  
[ event_source(com), coclass ]  
struct A  
{  
   __event __interface I;   // C3732  
};  
  
int main()  
{  
}  
```