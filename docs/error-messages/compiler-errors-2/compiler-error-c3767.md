---
title: "컴파일러 오류 c&3767; | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3767
dev_langs:
- C++
helpviewer_keywords:
- C3767
ms.assetid: 5247cdcd-639c-4527-bd37-37e74c4e8fab
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: b0cce511d895aae218c1b2ab04d129173b049983
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3767"></a>컴파일러 오류 C3767
'function' 후보 함수에 액세스할 수 없습니다.  
  
 Friend 함수는 클래스에 정의 된 경우 정의 되 고 전역 네임 스페이스 범위에서 선언 된 것으로 처리 해서는 안 됩니다. 그러나 인수 종속성 조회에서 찾을 수, 그 수 있습니다.  
  
 C&3767; 주요 변경에 의해서도 발생할 수 있습니다: 네이티브 형식은 이제 전용 형식에 기본적으로는 **/clr** 컴파일; 참조 [가시성 입력](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) 에 대 한 자세한 내용은 합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 c&3767; 오류가 생성 됩니다.  
  
```  
// C3767a.cpp  
// compile with: /clr  
using namespace System;  
public delegate void TestDel();  
  
public ref class MyClass {  
public:  
   static event TestDel^ MyClass_Event;  
};  
  
public ref class MyClass2 : public MyClass {  
public:  
   void Test() {  
      MyClass^ patient = gcnew MyClass;  
      patient->MyClass_Event();  
    }  
};  
  
int main() {  
   MyClass^ x = gcnew MyClass;  
   x->MyClass_Event();   // C3767  
  
   // OK  
   MyClass2^ y = gcnew MyClass2();  
   y->Test();  
};  
```  
  
 다음 샘플에서는 c&3767; 오류가 생성 됩니다.  
  
```  
// C3767c.cpp  
// compile with: /clr /c  
  
ref class Base  {  
protected:  
   void Method() {  
      System::Console::WriteLine("protected");  
   }  
};  
  
ref class Der : public Base {  
   void Method() {  
      ((Base^)this)->Method();   // C3767  
      // try the following line instead  
      // Base::Method();  
   }  
};  
```  
  
 Visual c + +.NET 2002 컴파일러 기호를 조회 하는 방법을 변경 합니다. 경우에 따라 것은 자동으로 알아보았습니다 지정된 된 네임 스페이스의 기호에 대 한 합니다. 이제, 인수 종속성 조회를 사용합니다.  
  
 다음 샘플에서는 c&3767; 오류가 생성 됩니다.  
  
```  
// C3767e.cpp  
namespace N {  
   class C {  
      friend void FriendFunc() {}  
      friend void AnotherFriendFunc(C* c) {}  
   };  
}  
  
int main() {  
   using namespace N;  
   FriendFunc();   // C3767 error  
   C* pC = new C();  
   AnotherFriendFunc(pC);   // found via argument-dependent lookup  
}  
```  
  
 Visual c + +.NET 2003 및 Visual c + +.NET 2002에서 유효한 코드에 대 한 friend 클래스 범위에서 선언 하 고 네임 스페이스 범위에 정의 합니다.  
  
```  
// C3767f.cpp  
class MyClass {  
   int m_private;  
   friend void func();  
};  
  
void func() {  
   MyClass s;  
   s.m_private = 0;  
}  
  
int main() {  
   func();  
}  
```
