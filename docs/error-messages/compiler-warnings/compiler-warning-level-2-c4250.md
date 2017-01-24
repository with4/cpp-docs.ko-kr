---
title: "컴파일러 경고 (수준 2) C4250 | Microsoft Docs"
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
  - "C4250"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4250"
ms.assetid: d47f7249-6b5a-414b-b2d4-56e5d246a782
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 2) C4250
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class1' : 우위에 따라 'class2::member'을\(를\) 상속합니다.  
  
 두 개 이상의 멤버 이름이 동일합니다.  `class2`은\(는\) 이 멤버를 포함하고 있는 다른 클래스에 대한 기본 클래스이므로 해당 클래스에 있는 멤버 중 하나는 상속된 것입니다.  
  
 C4250을 비활성화하려면 [경고](../../preprocessor/warning.md) pragma를 사용하십시오.  
  
 가상 기본 클래스는 여러 파생 클래스 사이에 공유되므로 파생 클래스의 이름은 기본 클래스의 이름보다 우위를 차지합니다.  예를 들어, 클래스 계층 구조가 다음과 같은 경우 diamond 내에서 상속되는 함수의 정의는 두 가지입니다. vbc::func\(\) 인스턴스는 약한 클래스를 통해 상속되고 dominant::func\(\)는 우위 클래스를 통해 상속됩니다.  diamond 클래스 개체를 통한 func\(\)의 비정규화된 호출은 항상 dominate::func\(\) 인스턴스를 호출합니다.  약한 클래스에서 func\(\)의 인스턴스를 정의해야 하는 경우 어떠한 정의도 우위를 차지하지 않으며 이 호출은 모호한 것으로 플래그가 지정됩니다.  
  
```  
// C4250.cpp  
// compile with: /c /W2  
#include <stdio.h>  
struct vbc {  
   virtual void func() { printf("vbc::func\n"); }  
};  
  
struct weak : public virtual vbc {};  
  
struct dominant : public virtual vbc {  
   void func() { printf("dominant::func\n"); }  
};  
  
struct diamond : public weak, public dominant {};  
  
int main() {  
   diamond d;  
   d.func();   // C4250  
}  
```  
  
## 예제  
 다음 샘플에서는 C4250 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4250_b.cpp  
// compile with: /W2 /EHsc  
#include <iostream>  
using namespace std;  
class A {  
public:  
   virtual operator int () {  
      return 2;  
   }  
};  
  
class B : virtual public A {  
public:  
   virtual operator int () {  
      return 3;  
   }  
};  
  
class C : virtual public A {};  
  
class E : public B, public C {};   // C4250  
  
int main() {  
   E eObject;  
   cout << eObject.operator int() << endl;  
}  
```  
  
## 예제  
 이 샘플에서는 더 복잡한 상황을 보여 줍니다.  다음 샘플에서는 C4250 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4250_c.cpp  
// compile with: /W2 /EHsc  
#include <iostream>  
using namespace std;  
  
class V {  
public:  
   virtual int f() {  
      return 1024;  
   }  
};  
  
class B : virtual public V {  
public:  
   int b() {  
      return f(); // B::b() calls V::f()  
   }  
};  
  
class M : virtual public V {  
public:  
   int f() {  
      return 7;  
   }  
};  
  
// because of dominance, f() is M::f() inside D,  
// changing the meaning of B::b's f() call inside a D  
class D : public B, public M {};   // C4250  
  
int main() {  
   D d;  
   cout << "value is: " << d.b();   // invokes M::f()  
}  
```