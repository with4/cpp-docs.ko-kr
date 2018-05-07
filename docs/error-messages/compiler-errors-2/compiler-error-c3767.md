---
title: 컴파일러 오류 C3767 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3767
dev_langs:
- C++
helpviewer_keywords:
- C3767
ms.assetid: 5247cdcd-639c-4527-bd37-37e74c4e8fab
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2e7e5e422206f3ee58b95024a3b96244d848e1b0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3767"></a>컴파일러 오류 C3767
'function' 후보 함수에 액세스할 수 없습니다.  
  
 클래스에 정의 된 friend 함수 정의 하며, 전역 네임 스페이스 범위에서 선언 된 경우 처럼 처리 해서는 안 됩니다. 그러나 인수 종속 조회에서 찾을 수, 그 수 있습니다.  
  
 C3767 주요 변경 내용으로 발생할 수 있습니다: 네이티브 형식에 기본적으로 private 됩니다는 **/clr** 컴파일 시 참조 [표시 유형 입력](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) 에 대 한 자세한 내용은 합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3767 오류가 생성 됩니다.  
  
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
  
 다음 샘플에서는 C3767 오류가 생성 됩니다.  
  
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
  
 