---
title: "컴파일러 오류 C3136 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3136
dev_langs:
- C++
helpviewer_keywords:
- C3136
ms.assetid: c77103cd-00f7-408e-b74b-4f8562039d31
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 9e6a8e3c958c6c1293b20451f632910001ef24f2
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3136"></a>컴파일러 오류 C3136
'interface': COM 인터페이스를 다른 COM 인터페이스에서 에서만 상속할 수 있습니다, 'interface' COM 인터페이스가 아니므로  
  
 적용 된 인터페이스는 [인터페이스 특성](../../windows/interface-attributes.md) 인터페이스를 COM 인터페이스에서 상속 합니다. COM 인터페이스에서 궁극적으로 상속 `IUnknown`합니다. 인터페이스 특성 다음에 오는 인터페이스가 COM 인터페이스가입니다.  
  
 다음 예제에서는 C3136 오류가 생성 됩니다.  
  
```  
// C3136.cpp  
#include "unknwn.h"  
  
__interface A   // C3136  
// try the following line instead  
// _interface A : IUnknown  
{  
   int a();  
};  
  
[object]  
__interface B : A  
{  
   int aa();  
};  
```
