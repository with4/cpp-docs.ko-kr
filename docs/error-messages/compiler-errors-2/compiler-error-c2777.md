---
title: 컴파일러 오류 C2777 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2777
dev_langs:
- C++
helpviewer_keywords:
- C2777
ms.assetid: 5fe158c0-2a65-488a-aca2-61d4a8b32d43
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cc3eebe5d3fe12bf102adff0cc77b6647fcf2059
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2777"></a>컴파일러 오류 C2777
속성 당 'put' 메서드를 하나만 지정할 수 있습니다.  
  
 A [속성](../../cpp/property-cpp.md) declspec 한정자가 둘 이상의 `put` 속성입니다.  
  
 다음 샘플에서는 C2777 오류가 생성 됩니다.  
  
```  
// C2777.cpp  
struct A {  
   __declspec(property(put=PutProp,put=PutPropToo))   // C2777  
   // try the following line instead  
   // __declspec(property(put=PutProp))  
      int prop;  
   int PutProp(void);  
   int PutPropToo(void);  
};  
```