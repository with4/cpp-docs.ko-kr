---
title: "인터페이스 클래스 (c + + 구성 요소 확장명) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: interface_CPP
dev_langs: C++
helpviewer_keywords:
- interface class keyword
- interface struct keyword
ms.assetid: 3ccea701-f50b-4da7-ad6b-f0ee1203e2b9
caps.latest.revision: "30"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: abe4173dabd20442b96c8e5536b040483df4f150
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="interface-class--c-component-extensions"></a>interface 클래스(C++ 구성 요소 확장)
인터페이스를 선언합니다.  네이티브 인터페이스에 대 한 자세한 내용은 참조 [__interface](../cpp/interface.md)합니다.  
  
## <a name="all-runtimes"></a>모든 런타임  
 **구문**  
  
```  
  
interface_access  
interface class  
 name :  inherit_accessbase_interface{};interface_accessinterface structname :  inherit_accessbase_interface{};  
```  
  
 **매개 변수**  
  
 *interface_access*  
 어셈블리 외부에서 인터페이스의 접근성입니다.  가능한 값은 **공용** 및 `private`합니다.  기본값은 `private`입니다.  중첩 된 인터페이스를 사용할 수 없습니다는 *interface_access* 지정자입니다.  
  
 *name*  
 인터페이스의 이름입니다.  
  
 *inherit_access*  
 액세스 가능성 *base_interface*합니다.  유일한 허용 내게 필요한 옵션은 기본 인터페이스에 대 한 `public` (기본값).  
  
 *base_interface* (선택 사항)  
 인터페이스에 대 한 기본 인터페이스 *이름*합니다.  
  
 **주의**  
  
 **구조체 인터페이스** 같습니다 **인터페이스 클래스**합니다.  
  
 인터페이스는 함수, 이벤트 및 속성에 대 한 선언을 포함할 수 있습니다.  모든 인터페이스 멤버는 public 액세스 가능성을 갖습니다. 인터페이스는 정적 데이터 멤버, 함수, 이벤트 및 속성에도 포함 될 수 있습니다 및 이러한 정적 멤버는 인터페이스에 정의 되어야 합니다.  
  
 인터페이스는 클래스 수 구현 하는 방법을 정의 합니다. 인터페이스 클래스 아니며 클래스만 인터페이스를 구현할 수 있습니다. 클래스 인터페이스에 선언 된 함수를 정의 하는 경우 재정의 되지 함수 구현 됩니다. 따라서 이름 조회는 인터페이스 멤버를 포함 되지 않습니다.  
  
 클래스 또는 구조체는 인터페이스에서 파생 되는 인터페이스의 모든 멤버를 구현 해야 합니다. 인터페이스를 구현할 때 *이름* 의 인터페이스를 구현 해야는 `base_interface` 목록입니다.  
  
 자세한 내용은 다음을 참조하세요.  
  
-   [인터페이스 정적 생성자](../dotnet/how-to-define-an-interface-static-constructor-cpp-cli.md)  
  
-   [제네릭 인터페이스(Visual C++)](../windows/generic-interfaces-visual-cpp.md)  
  
 다른 CLR 형식에 대 한 자세한 내용은 참조 하십시오. [클래스 및 구조체](../windows/classes-and-structs-cpp-component-extensions.md)합니다.  
  
 형식이와 인터페이스 하는 경우 컴파일 타임에 감지할 수 `__is_interface_class(type)`합니다. 자세한 내용은 참조 [형식 특성에 대 한 컴파일러 지원](../windows/compiler-support-for-type-traits-cpp-component-extensions.md)합니다.  
  
 개발 환경에서 있습니다 수 F1 도움말을 볼 이러한 키워드는 키워드를 강조 표시 하 여 (`interface class`예를 들면) F1 키를 눌러 합니다.  
  
## <a name="windows-runtime"></a>Windows 런타임  
 **주의**  
  
 (이 언어 기능에는 Windows 런타임에만 적용되는 설명이 없습니다.)  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: **/ZW**  
  
## <a name="common-language-runtime"></a>공용 언어 런타임 
 **주의**  
  
 (이 언어 기능에는 공용 언어 런타임에만 적용되는 설명이 없습니다.)  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: **/clr**  
  
### <a name="examples"></a>예제  
 **예제**  
  
 다음 코드 예제에서는 인터페이스 수 clock 함수 동작을 정의 하는 방법을 보여 줍니다.  
  
```  
// mcppv2_interface_class.cpp  
// compile with: /clr  
using namespace System;  
  
public delegate void ClickEventHandler(int, double);  
  
// define interface with nested interface  
public interface class Interface_A {  
   void Function_1();  
  
   interface class Interface_Nested_A {  
      void Function_2();  
   };  
};  
  
// interface with a base interface  
public interface class Interface_B : Interface_A {  
   property int Property_Block;  
   event ClickEventHandler^ OnClick;     
   static void Function_3() { Console::WriteLine("in Function_3"); }  
};  
  
// implement nested interface  
public ref class MyClass : public Interface_A::Interface_Nested_A {  
public:  
   virtual void Function_2() { Console::WriteLine("in Function_2"); }  
};  
  
// implement interface and base interface  
public ref class MyClass2 : public Interface_B {  
private:  
   int MyInt;  
  
public:  
   // implement non-static function  
   virtual void Function_1() { Console::WriteLine("in Function_1"); }  
  
   // implement property  
   property int Property_Block {  
      virtual int get() { return MyInt; }  
      virtual void set(int value) { MyInt = value; }  
   }  
   // implement event  
   virtual event ClickEventHandler^ OnClick;  
  
   void FireEvents() {  
      OnClick(7, 3.14159);  
   }  
};  
  
// class that defines method called when event occurs  
ref class EventReceiver {  
public:  
   void OnMyClick(int i, double d) {  
      Console::WriteLine("OnClick: {0}, {1}", i, d);  
   }  
};  
  
int main() {  
   // call static function in an interface  
   Interface_B::Function_3();  
  
   // instantiate class that implements nested interface  
   MyClass ^ x = gcnew MyClass;  
   x->Function_2();  
  
   // instantiate class that implements interface with base interface  
   MyClass2 ^ y = gcnew MyClass2;  
   y->Function_1();  
   y->Property_Block = 8;  
   Console::WriteLine(y->Property_Block);  
  
   EventReceiver^ MyEventReceiver = gcnew EventReceiver();  
  
   // hook handler to event  
   y->OnClick += gcnew ClickEventHandler(MyEventReceiver, &EventReceiver::OnMyClick);  
  
   // invoke events  
   y->FireEvents();  
  
   // unhook handler to event  
   y->OnClick -= gcnew ClickEventHandler(MyEventReceiver, &EventReceiver::OnMyClick);  
  
   // call implemented function via interface handle  
   Interface_A^ hi = gcnew MyClass2();  
   hi->Function_1();  
}  
```  
  
 **출력**  
  
```Output  
in Function_3  
  
in Function_2  
  
in Function_1  
  
8  
  
OnClick: 7, 3.14159  
  
in Function_1  
```  
  
 **예제**  
  
 다음 코드 예제에는 여러 인터페이스에 및 이러한 인터페이스는 클래스에 의해 사용 되는 위치를 선언 하는 동일한 서명으로 함수를 구현 하는 두 가지 방법으로 보여 줍니다.  
  
```  
// mcppv2_interface_class_2.cpp  
// compile with: /clr /c  
interface class I {  
   void Test();  
   void Test2();  
};  
  
interface class J : I {  
   void Test();  
   void Test2();  
};  
  
ref struct R : I, J {  
   // satisfies the requirement to implement Test in both interfaces  
   virtual void Test() {}  
  
   // implement both interface functions with explicit overrides  
   virtual void A() = I::Test2 {}  
   virtual void B() = J::Test2 {}  
};  
```  
  
## <a name="see-also"></a>참고 항목  
 [런타임 플랫폼용 구성 요소 확장](../windows/component-extensions-for-runtime-platforms.md)