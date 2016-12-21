---
title: "컴파일러 오류 C2680 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2680"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2680"
ms.assetid: d6f7129e-dd17-4661-b680-18d6b925b1cc
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2680
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : 이름의 대상 형식이 잘못되었습니다.  
  
 캐스팅 연산자가 포인터 또는 참조가 아닌 형식으로 변환하려고 했습니다.  [dynamic\_cast](../../cpp/dynamic-cast-operator.md) 연산자는 포인터 또는 참조에만 사용할 수 있습니다.  
  
 다음 샘플에서는 C2680 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2680.cpp  
// compile with: /c  
class A { virtual void f(); };  
class B : public A {};  
  
void g(B b) {  
   A a;  
   a = dynamic_cast<A>(b);   // C2680  target not a reference type  
   a = dynamic_cast<A&>(b);   // OK  
}  
```  
  
 C2680은 대상을 정의하지 않은 경우에도 발생할 수 있습니다.  
  
```  
// C2680b.cpp  
// compile with: /clr /c  
// C2680 expected  
using namespace System::Collections;  
  
// Delete the following line to resolve.  
ref class A;   // not defined  
  
// Uncomment the following line to resolve.  
// ref class A{};  
  
public ref class B : ArrayList {  
   property A^ C[int] {  
      A^ get(int index) {  
         return dynamic_cast<A^>(this->default::get(index));  
      }  
      void set(int index, A^ value) {  
         this->default::set(index, value);   
      }  
   }  
};  
```