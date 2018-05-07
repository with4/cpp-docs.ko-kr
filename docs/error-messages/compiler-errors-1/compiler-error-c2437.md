---
title: 컴파일러 오류 C2437 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2437
dev_langs:
- C++
helpviewer_keywords:
- C2437
ms.assetid: 2d2b3c6c-856a-4b27-ae10-64813b3e5483
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dc9c619ac361fcbe2d095407b4030a2e38ada8ad
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2437"></a>컴파일러 오류 C2437
'identifier': 이미 초기화 되었습니다.  
  
 개체는 한 번만 초기화할 수 있습니다.  
  
 다음 샘플에서는 C2437 오류가 생성 됩니다.  
  
```  
// C2437.cpp  
// compile with: /c  
class A {  
public:  
   A(int i) {}  
};  
  
class B : A {  
   B() : A(1), A(2) {}   // C2437  
   B() : A(1) {}   // OK  
};  
```