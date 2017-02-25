---
title: "컴파일러 오류 C2247 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2247"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2247"
ms.assetid: 72efa03e-615e-4ef9-aede-0a98654b20fd
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# 컴파일러 오류 C2247
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier'에 액세스할 수 없습니다. 이는 'class'이\(가\) 'specifier'을\(를\) 사용하여 'class'에서 상속하기 때문입니다.  
  
 `identifier`가 private 또는 protected 액세스로 선언된 클래스에서 상속되었습니다.  
  
 다음 샘플에서는 C2247 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2247.cpp  
class A {  
public:  
   int i;  
};  
class B : private A {};    // B inherits a private A  
class C : public B {} c;   // so even though C's B is public  
int j = c.i;               // C2247, i not accessible  
```  
  
 Visual Studio .NET 2003에서는 컴파일러 규칙에 따라 이제 컨트롤에 액세스할 때 보호된 멤버를 사용하기 때문에 이 오류가 발생할 수도 있습니다.  보호된 멤버 n은 n이 멤버로 포함된 클래스 A에서 상속하는 클래스 B의 멤버 함수를 통해서만 액세스될 수 있습니다.  
  
 Visual Studio .NET 2003과 Visual Studio .NET 버전의 Visual C\+\+ 모두에서 올바른 코드가 되도록 하려면 멤버를 해당 형식의 Friend가 되도록 선언하십시오.  공용 상속을 사용할 수도 있습니다.  
  
```  
// C2247b.cpp  
// compile with: /c  
// C2247 expected  
class A {  
public:  
   void f();  
   int n;  
};  
  
class B: protected A {  
   // Uncomment the following line to resolve.  
   // friend void A::f();  
};  
  
void A::f() {  
   B b;  
   b.n;  
}  
```  
  
 Visual Studio .NET 2003에서는 컴파일러 규칙에 따라 이제 전용 기본 클래스에 액세스할 수 없기 때문에 C2247이 발생할 수도 있습니다.  형식 B의 전용 기본 클래스인 클래스 A는 B를 기본 클래스로 사용하는 형식 C에서 액세스할 수 없습니다.  
  
 Visual Studio .NET 2003과 Visual Studio .NET 버전의 Visual C\+\+ 모두에서 올바른 코드가 되도록 하려면 범위 연산자를 사용하십시오.  
  
```  
// C2247c.cpp  
// compile with: /c  
struct A {};  
  
struct B: private A {};  
  
struct C : B {  
   void f() {  
      A *p1 = (A*) this;   // C2247  
      // try the following line instead  
      // ::A *p2 = (::A*) this;  
   }  
};  
```