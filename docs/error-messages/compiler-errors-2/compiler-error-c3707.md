---
title: "컴파일러 오류 C3707 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3707
dev_langs:
- C++
helpviewer_keywords:
- C3707
ms.assetid: ac63a5dd-7a4b-48d2-9f2a-be9cb090134c
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 7167ea0df9bc0846de16be40d722c63bfea11c32
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3707"></a>컴파일러 오류 C3707
'function': dispinterface 메서드에 dispid가 있어야 합니다.  
  
 사용 하는 경우는 `dispinterface` 메서드를 할당 해야는 `dispid`합니다. 이 오류를 해결 하려면 할당는 `dispid` 에 `dispinterface` 을 주석으로 등의 메서드는 `id` 아래 예제에서 메서드에 특성을 합니다. 자세한 내용은 특성을 참조 하십시오. [dispinterface](../../windows/dispinterface.md) 및 [id](../../windows/id.md)합니다.  
  
 다음 샘플에서는 C3707 오류가 생성 됩니다.  
  
```  
// C3707.cpp  
#include <atlbase.h>  
#include <atlcom.h>  
#include <atlctl.h>  
  
[module(name="xx")];  
[dispinterface]  
__interface IEvents : IDispatch  
{  
   HRESULT event1([in] int i);   // C3707  
   // try the following line instead  
   // [id(1)] HRESULT event1([in] int i);  
};  
  
int main() {  
}  
```
