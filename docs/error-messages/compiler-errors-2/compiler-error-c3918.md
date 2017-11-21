---
title: "컴파일러 오류 C3918 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3918
dev_langs: C++
helpviewer_keywords: C3918
ms.assetid: a8b3a90a-3fe1-4244-a5ff-a31cdae97d98
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1bf9cf676cf7435eaf1f0b924fbadcaddef842b4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3918"></a>컴파일러 오류 C3918
사용 현황 데이터 멤버를 ' member' 필요  
  
 C3918은 이벤트와 관련 된 여러 가지 이유로 발생할 수 있습니다.  
  
## <a name="example"></a>예제  
 C3918은 클래스 멤버가 현재 컨텍스트에서 필요 하기 때문에 발생할 수 있습니다. 다음 샘플에서는 C3918 오류가 발생 합니다.  
  
```  
// C3918.cpp  
// compile with: /clr /c  
public ref class C {  
public:  
   System::Object ^ o;  
   delegate void Del();  
  
   event Del^ MyEvent {  
      void add(Del^ev) {  
         if ( MyEvent != nullptr) {}   // C3918  
         if ( o != nullptr) {}   // OK  
   }  
   void remove(Del^){}  
   }  
};  
```  
  
## <a name="example"></a>예제  
 C3918는 null (이벤트 이름을 더 이상에 직접 액세스할 지원 저장소 대리자는 이벤트에 대 한)에 대 한 trivial 이벤트를 확인 하려고 하는 경우에 발생 합니다.  
  
 다음 샘플에서는 C3918 오류가 발생 합니다.  
  
```  
// C3918_2.cpp  
// compile with: /clr /c  
using namespace System;  
public delegate int MyDel(int);  
  
interface struct IEFace {  
   event MyDel ^ E;  
};  
  
ref struct EventSource : public IEFace {  
   virtual event MyDel ^ E;  
   void Fire_E(int i) {  
      if (E)   // C3918  
         E(i);  
   }  
};  
```  
  
## <a name="example"></a>예제  
 C3918 올바르게 구독 하는 경우 하지 이벤트에도 발생할 수 있습니다. 다음 샘플에서는 C3918 오류가 발생 합니다.  
  
```  
// C3918_3.cpp  
// compile with: /clr /c  
using namespace System;  
  
public delegate void del();  
  
public ref class A {  
public:  
   event del^ e {  
      void add(del ^handler ) {  
         d += handler;  
      }  
  
      void remove(del ^handler) {  
         d -= handler;  
      }  
  
      void raise() {   
         d();  
      }  
   }  
  
   del^ d;  
   void f() {}  
  
   A() {  
      e = gcnew del(this, &A::f);   // C3918  
      // try the following line instead  
      // e += gcnew del(this, &A::f);  
      e();  
   }  
};  
  
int main() {  
   A a;  
}  
```