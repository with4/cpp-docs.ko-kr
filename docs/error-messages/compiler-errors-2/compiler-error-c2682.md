---
title: "컴파일러 오류 C2682 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2682
dev_langs: C++
helpviewer_keywords: C2682
ms.assetid: 30c6a7c4-f5f7-4fe8-81a8-c48938521ab4
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3df494f5d78a862e260fa4edfe0a2740e4fc8cdd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2682"></a>컴파일러 오류 C2682
'type1'에서 'type2'로 변환 하려면 casting_operator를 사용할 수 없습니다.  
  
 캐스팅 연산자 호환 되지 않는 형식 간에 변환 하려고 했습니다. 예를 들어 사용할 수 없습니다는 [dynamic_cast](../../cpp/dynamic-cast-operator.md) 참조에 대 한 포인터를 변환 하는 연산자입니다. `dynamic_cast` 한정자를 캐스팅 하는 연산자를 사용할 수 없습니다. 모든 한정자의 형식이 일치 해야 합니다.  
  
 사용할 수는 `const_cast` 연산자와 같은 특성을 제거 하려면 `const`, `volatile`, 또는 `__unaligned`합니다.  
  
 다음 샘플에서는 C2682 오류가 생성 됩니다.  
  
```  
// C2682.cpp  
class A { virtual void f(); };  
class B: public A {};  
  
void g(A* pa) {  
    B& rb = dynamic_cast<B&>(pa); // C2682  
}  
```  
  
 다음 샘플에서는 C2682 오류가 생성 됩니다.  
  
```  
// C2682b.cpp  
// compile with: /clr  
ref struct R{};  
ref struct RR : public R{};  
ref struct H {  
   RR^ r ;  
   short s;  
   int i;  
};  
  
int main() {  
   H^ h = gcnew H();    
   interior_ptr<int>lr = &(h->i);  
   interior_ptr<short>ssr = safe_cast<interior_ptr<short> >(lr);   // C2682  
   interior_ptr<short>ssr = reinterpret_cast<interior_ptr<short> >(lr);   // OK  
}  
```