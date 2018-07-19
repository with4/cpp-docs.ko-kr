---
title: 컴파일러 오류 C2602 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2602
dev_langs:
- C++
helpviewer_keywords:
- C2602
ms.assetid: 6c07a40e-537e-4954-b5c5-1e0e58fe1952
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 07fd581d8d95ae33ba2a38ea45a458f2085e0ef1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33229305"
---
# <a name="compiler-error-c2602"></a>컴파일러 오류 C2602
'class::Identifier' 'class'의 기본 클래스의 구성원이 아닙니다.  
  
 `Identifier` 클래스는 기본 클래스에서 상속 된 멤버가 없기 때문에 액세스할 수 없습니다.  
  
 다음 샘플에서는 C2602 오류가 생성 됩니다.  
  
```  
// C2602.cpp  
// compile with: /c  
struct X {  
   int x;  
};  
struct A {  
   int a;  
};  
struct B : public A {  
   X::x;   // C2602 B is not derived from X  
   A::a;   // OK  
};  
```