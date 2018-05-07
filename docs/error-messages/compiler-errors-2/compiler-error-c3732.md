---
title: 컴파일러 오류 C3732 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3732
dev_langs:
- C++
helpviewer_keywords:
- C3732
ms.assetid: 2d55a7e1-9c39-4379-a093-2f7beb27e2ca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8b6b5c66ba02bdb23e5b8dffe6f0ba74350b2e32
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3732"></a>컴파일러 오류 C3732
'interface': COM 이벤트를 발생 시키는 사용자 지정 인터페이스는 IDispatch에서 상속할 수 없습니다  
  
 지 원하는 COM 이벤트 인터페이스에서 상속할 수 없습니다 `IDispatch`합니다. 자세한 내용은 참조 [COM에서 이벤트 처리](../../cpp/event-handling-in-com.md)합니다.  
  
 다음 오류 C3732를 생성합니다.  
  
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