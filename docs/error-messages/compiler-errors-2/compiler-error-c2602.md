---
title: "컴파일러 오류 C2602 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2602
dev_langs:
- C++
helpviewer_keywords:
- C2602
ms.assetid: 6c07a40e-537e-4954-b5c5-1e0e58fe1952
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: a6b34901c2585d06f5ca5c50e16455879bfa3a0b
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2602"></a>컴파일러 오류 C2602
'class::Identifier' 'class'의 기본 클래스의 구성원이 아닙니다.  
  
 `Identifier`클래스는 기본 클래스에서 상속 된 멤버가 없기 때문에 액세스할 수 없습니다.  
  
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
