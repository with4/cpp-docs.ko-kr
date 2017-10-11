---
title: "컴파일러 오류 C2776 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2776
dev_langs:
- C++
helpviewer_keywords:
- C2776
ms.assetid: 9d80addc-62c7-40fc-a2cc-60303abb87df
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 5642335519263c3b191d1c14399f3d00f366a8c9
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2776"></a>컴파일러 오류 C2776
속성 당 'get' 메서드를 하나만 지정할 수 있습니다.  
  
 만 지정할 수 있습니다 `get` 함수는 [속성](../../cpp/property-cpp.md) 확장된 특성입니다. 이 오류가 발생할 때 여러 `get` 함수를 지정 합니다.  
  
 다음 샘플에서는 C2776 오류가 생성 됩니다.  
  
```  
// C2776.cpp  
struct A {  
   __declspec(property(get=GetProp,get=GetPropToo))  
   // try the following line instead  
   // __declspec(property(get=GetProp))  
      int prop;   // C2776  
   int GetProp(void);  
   int GetPropToo(void);  
};  
```
