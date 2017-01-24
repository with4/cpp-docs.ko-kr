---
title: "컴파일러 경고 (수준 4) C4487 | Microsoft Docs"
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
  - "C4487"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4487"
ms.assetid: 796144cf-cd3c-4edc-b6a4-96192b7eb4f0
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 4) C4487
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'derived\_class\_function' : 상속된 비가상 메서드 'base\_class\_function'과\(와\) 일치하지만 명시적으로 'new'로 표시되어 있지 않습니다.  
  
 파생 클래스에 있는 함수의 시그니처가 비가상 기본 클래스 함수의 시그니처와 동일합니다.  C4487은 파생 클래스 함수는 기본 클래스 함수를 재정의하지 않음을 나타냅니다.  이 경고를 해결하려면 파생 클래스 함수를 명시적으로 `new`로 표시하십시오.  
  
 자세한 내용은 [new \(new slot in vtable\)](../../windows/new-new-slot-in-vtable-cpp-component-extensions.md)을 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C4487 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4487.cpp  
// compile with: /W4 /clr  
using namespace System;  
public ref struct B {  
   void f() { Console::WriteLine("in B::f"); }  
   void g() { Console::WriteLine("in B::g"); }  
};  
  
public ref struct D : B {  
   void f() { Console::WriteLine("in D::f"); }   // C4487  
   void g() new { Console::WriteLine("in D::g"); }   // OK  
};  
  
int main() {  
   B ^ a = gcnew D;  
   // will call base class functions  
   a->f();  
   a->g();  
}  
```