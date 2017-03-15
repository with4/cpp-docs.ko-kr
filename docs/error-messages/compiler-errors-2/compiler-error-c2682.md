---
title: "컴파일러 오류 C2682 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2682"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2682"
ms.assetid: 30c6a7c4-f5f7-4fe8-81a8-c48938521ab4
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# 컴파일러 오류 C2682
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

casting\_operator을\(를\) 사용하여 'type1'에서 'type2'\(으\)로 변환할 수 없습니다.  
  
 캐스팅 연산자가 호환되지 않는 형식 간에 변환하려고 했습니다.  예를 들어, [dynamic\_cast](../../cpp/dynamic-cast-operator.md) 연산자를 사용하여 포인터를 참조로 변환할 수 없습니다.  `dynamic_cast` 연산자를 사용하여 한정자를 버릴 수 없습니다.  모든 한정자의 형식이 일치해야 합니다.  
  
 `const_cast` 연산자를 사용하면 `const`, `volatile` 또는 `__unaligned`와 같은 특성을 제거할 수 있습니다.  
  
 다음 샘플에서는 C2682 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2682.cpp  
class A { virtual void f(); };  
class B: public A {};  
  
void g(A* pa) {  
    B& rb = dynamic_cast<B&>(pa); // C2682  
}  
```  
  
 다음 샘플에서는 C2682 오류가 발생하는 경우를 보여 줍니다.  
  
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