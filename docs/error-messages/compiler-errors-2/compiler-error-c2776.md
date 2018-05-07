---
title: 컴파일러 오류 C2776 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2776
dev_langs:
- C++
helpviewer_keywords:
- C2776
ms.assetid: 9d80addc-62c7-40fc-a2cc-60303abb87df
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: afbf3c48e5445d101408c2539cc077071b639044
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
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