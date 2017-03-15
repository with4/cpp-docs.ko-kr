---
title: "컴파일러 오류 C2512 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2512"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2512"
ms.assetid: 15206da9-1164-451a-b869-280e00711aad
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2512
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier': 사용할 수 있는 적절한 기본 생성자가 없습니다.  
  
 지정된 클래스, 구조체 또는 공용 구조체에 사용할 수 있는 기본 생성자가 없습니다.  컴파일러는 사용자 정의 생성자가 제공되지 않는 경우에만 기본 생성자를 제공합니다.  
  
 void가 아닌 매개 변수를 사용하는 생성자를 제공하고 배열의 요소와 같이 매개 변수 없이 클래스를 만들 수 있도록 하려면 기본 생성자도 제공해야 합니다.  기본 생성자는 모든 매개 변수에 기본값을 사용하는 생성자일 수 있습니다.  
  
 다음 샘플에서는 C2512를 생성하고 해결 방법을 보여 줍니다.  
  
```  
// C2512.cpp  
// C2512 expected  
struct B {  
   B (char *);  
   // Uncomment the following line to fix.  
   // B() {};  
};  
  
int main() {  
   B b;   
}  
```  
  
 다음 샘플에서는 더 미묘한 C2512를 보여 줍니다.  이 오류를 해결하려면 해당 생성자가 참조되기 전에 클래스를 정의하도록 코드를 다시 정렬합니다.  
  
```  
// C2512b.cpp  
// compile with: /c  
struct S {  
   struct X;  
  
   void f() {  
      X *x = new X();   // C2512 X not defined yet  
   }  
  
};  
  
struct S::X {};  
  
struct T {  
   struct X;  
   void f();  
};  
  
struct T::X {};  
  
void T::f() {  
   X *x = new X();  
}  
```  
  
 C2512는 const 또는 참조 데이터 멤버가 포함된 클래스를 기본 생성자로 호출해도 발생할 수 있습니다.  이러한 멤버를 생성자 이니셜라이저 목록에서 초기화하여 컴파일러에서 기본 생성자를 생성할 수 없도록 해야 합니다.  
  
 다음 샘플에서는 C2512를 생성하고 해결 방법을 보여 줍니다.  
  
```  
// C2512c.cpp  
// Compile by using: cl /c /W3 C2512c.cpp  
struct S {  
   const int i_;  
   int &r_;   
};   
  
int SumS() {  
   const int ci = 7;  
   int ir = 42;  
  
   S s1; // C2512 - no default constructor available  
   S s2{ci, ir};  // Fix - initialize const and reference members   
   return s2.i_ + s2.r_;  
}  
```