---
title: "컴파일러 경고 (수준 1) C4358 | Microsoft Docs"
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
  - "C4358"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4358"
ms.assetid: a9848f84-14b3-405e-81bf-ee3e91a51511
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4358
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator': 결합 대리자의 반환 형식이 'void'가 아닙니다. 반환된 값이 정의되지 않습니다.  
  
 두 대리자가 결합되었으며 반환 값이 void가 아닙니다.  반환 값이 void가 아닌 두 대리자를 결합하면 대리자의 반환 값이 사용되는 경우 컴파일러에서 할당을 올바르게 수행할 수 없습니다.  
  
 다음 샘플에서는 C4358 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4358.cpp  
// compile with: /clr /W1  
delegate int D();  
delegate void E();  
  
ref class X {  
   int i;  
public:  
   X(int ii) : i(ii) {}  
   int f() {  
      return i;  
   }  
};  
  
ref class Y {  
   int i;  
public:  
   Y() {}  
   void g() {}  
};  
  
int main() {  
   D^ d = gcnew D(gcnew X(1), &X::f);  
   D^ d2 = gcnew D(gcnew X(2), &X::f);  
  
   d += d2;   // C4358  
   int j = d();   // return value indeterminate  
  
   E^ e = gcnew E(gcnew Y, &Y::g);  
   E^ e2 = gcnew E(gcnew Y, &Y::g);  
   e += e2;   // OK  
}  
```