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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6a51ff76a635c1c55b0a12c28c8f1d93360dee6f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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