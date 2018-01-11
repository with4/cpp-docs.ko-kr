---
title: "컴파일러 경고 (수준 2) C4250 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4250
dev_langs: C++
helpviewer_keywords: C4250
ms.assetid: d47f7249-6b5a-414b-b2d4-56e5d246a782
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d92a337e3ded4b958bb9d1dbb7359d21f28d619c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-2-c4250"></a>컴파일러 경고(수준 2) C4250
'class1': 'class2::member' 우위를 통해 상속  
  
 둘 이상의 멤버가 이름이 같은 합니다. `class2` 이 멤버를 포함 하는 다른 클래스에 대 한 기본 클래스 이기 때문에 상속 됩니다.  
  
 C4250 하지 않으려면는 [경고](../../preprocessor/warning.md) pragma입니다.  
  
 가상 기본 클래스에서 파생된 되는 여러 클래스 간에 공유 파생된 클래스에서 이름이 기본 클래스에는 이름 보다 우위를 차지 합니다. 예를 들어 다음과 같은 클래스 계층 구조를 지정 된 경우 두 가지 방법이 다이아몬드에서 상속 하는 f: 약한 클래스 및 기준 클래스를 통해 되 통해 vbc::func() 인스턴스. 다이아몬드 클래스 개체를 통해 되는 정규화 되지 않은 호출 dominate 되 인스턴스를 항상 호출 합니다.  약한 클래스 되의 인스턴스, 모두 정의 우위를 차지 하는 경우 호출 모호한 것으로 플래그가 지정 됩니다.  
  
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
  
## <a name="example"></a>예  
 다음 샘플에서는 C4250 오류가 발생 합니다.  
  
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
  
## <a name="example"></a>예  
 이 예제에는 더 복잡 한 상황을 보여 줍니다. 다음 샘플에서는 C4250 오류가 발생 합니다.  
  
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