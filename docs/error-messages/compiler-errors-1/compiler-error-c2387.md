---
title: "컴파일러 오류 C2387 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2387"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2387"
ms.assetid: 6847b8e1-ffac-458d-ab88-0c92f72f2527
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2387
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : 모호한 기본 클래스  
  
 함수가 여러 기본 클래스에 있으므로 컴파일러에서 함수를 명확하게 확인할 수 없습니다.  
  
 이 오류를 해결하려면 기본 클래스 중 하나를 상속에서 제거하거나 함수 호출을 명시적으로 한정해야 합니다.  
  
 다음 샘플에서는 C2387 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2387.cpp  
namespace N1 {  
   struct B {  
      virtual void f() {  
      }  
   };  
}  
  
namespace N2 {  
   struct B {  
      virtual void f() {  
      }  
   };  
}  
  
struct D : N1::B, N2::B {  
   virtual void f() {  
      B::f();   // C2387  
      // try the following line instead  
      // N1::B::f();  
   }  
};  
  
int main() {  
   D aD;  
   aD.f();  
}  
```