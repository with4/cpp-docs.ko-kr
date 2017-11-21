---
title: "컴파일러 오류 C2680 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2680
dev_langs: C++
helpviewer_keywords: C2680
ms.assetid: d6f7129e-dd17-4661-b680-18d6b925b1cc
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f3a7d58aa7eb126392a0484ce28753c477d6137c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2680"></a>컴파일러 오류 C2680
'type': 이름에 대 한 잘못 된 대상 형식  
  
 캐스팅 연산자는 포인터 또는 참조 되지 않는 형식으로 변환 하려고 했습니다. [dynamic_cast](../../cpp/dynamic-cast-operator.md) 연산자는 포인터 또는 참조에 대해서만 사용할 수 있습니다.  
  
 다음 샘플에서는 c 2680 오류가 생성 됩니다.  
  
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
  
 C2680은 대상이 정의 되지 않은 경우에 발생할 수 있습니다.  
  
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