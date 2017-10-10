---
title: "컴파일러 오류 C2683 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2683
dev_langs:
- C++
helpviewer_keywords:
- C2683
ms.assetid: db605e4f-601b-4d05-92a1-c43ca24de08d
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: b3e79c1a05ac0d1fab713e2dfa97c9da740088bb
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2683"></a>컴파일러 오류 C2683
'cast': 'type' 다형 형식이 아닙니다  
  
 사용할 수 없습니다 [dynamic_cast](../../cpp/dynamic-cast-operator.md) 비 다형 클래스 (가상 함수가 없는 클래스)으로 변환할 수 있습니다.  
  
 사용할 수 있습니다 [static_cast](../../cpp/static-cast-operator.md) 을 비 다형 형식을 변환 합니다. 그러나 `static_cast` 런타임 검사를 수행 하지 않습니다.  
  
 다음 샘플에서는 C2683 오류가 생성 됩니다.  
  
```  
// C2683.cpp  
// compile with: /c  
class B { };  
class D : public B { };  
  
void f(B* pb) {  
   D* pd1 = dynamic_cast<D*>(pb);  // C2683  
   D* pd1 = static_cast<D*>(pb);   // OK  
}  
```
