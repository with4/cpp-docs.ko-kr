---
title: "interface class  (C++ Component Extensions) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "interface_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "interface class keyword"
  - "interface struct keyword"
ms.assetid: 3ccea701-f50b-4da7-ad6b-f0ee1203e2b9
caps.latest.revision: 30
caps.handback.revision: 28
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# interface class  (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

인터페이스를 선언합니다.  네이티브 인터페이스에 대한 자세한 내용은 [인터페이스](../cpp/interface.md)를 참조하십시오.  
  
## 모든 런타임  
 **구문**  
  
```  
  
        interface_access interface class  name :  inherit_access base_interface {};  
interface_access interface struct name :  inherit_access base_interface {};  
```  
  
 **매개 변수**  
  
 *interface\_access*  
 어셈블리 외부에서 인터페이스의 액세스 가능성입니다.  가능한 값은 **public** 및 `private`이고 기본값은 `private`입니다.  중첩된 인터페이스는  *interface\_access*  지정자를 사용할 수 없습니다.  
  
 *name*  
 인터페이스의 이름입니다.  
  
 *inherit\_access*  
 *base\_interface*의 액세스 가능성.  기본 인터페이스에 대한 허용된 필요한 옵션은  `public`  \(기본값\)인 경우뿐입니다.  
  
 *base\_interface*\(선택적 요소\)  
 *name*  인터페이스의 기본 인터페이스.  
  
 **설명**  
  
 **구조체 인터페이스**는 **인터페이스 클래스**에 해당합니다.  
  
 인터페이스는 함수, 이벤트 및 속성에 대한 선언이 포함될 수 있습니다.  모든 인터페이스 멤버는 공용 액세스 가능성을 포함합니다.  정적 데이터 멤버, 함수, 이벤트 및 속성을 인터페이스에 포함될 수도 있습니다. 인터페이스는 이러한 정적 멤버를 정의해야 합니다.  
  
 인터페이스는 클래스는 구현하는 방법을 정의합니다.  인터페이스는 클래스가 아닙니다. 클래스는 오직 인터페이스만을 구현할 수 있습니다.  클래스 인터페이스에 선언 된 함수를 정의하는 경우 재정의되지 않은 함수 구현됩니다.  따라서 이름 조회는 인터페이스 멤버를 포함하지 않습니다.  
  
 인터페이스에서 상속되는 클래스나 상수는 모든 인터페이스 멤버를 구현해야 합니다.  *이름* 인터페이스를 구현할 때,  `base_interface`  목록에 인터페이스를 반드시 구현해야 합니다.  
  
 자세한 내용은 다음을 참조하십시오.  
  
-   [인터페이스 정적 생성자](../dotnet/how-to-define-an-interface-static-constructor-cpp-cli.md)  
  
-   [Generic Interfaces \(Visual C\+\+\)](../windows/generic-interfaces-visual-cpp.md)  
  
 다른 CLR 형식에 대한 정보를 보려면  [클래스와 구조체](../windows/classes-and-structs-cpp-component-extensions.md)를 참조하십시오.  
  
 `__is_interface_class(`   `type`   `)` 형식이 있는 경우 컴파일 타임을 감지할 수 있습니다.  자세한 내용은 [Compiler Support for Type Traits](../windows/compiler-support-for-type-traits-cpp-component-extensions.md)을 참조하십시오.  
  
 개발 환경에서 키워드를 강조 표시하여\(예: `interface class`\) F1을 누르면 키워드에 대한 F1 도움말을 볼 수 있습니다.  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 **설명**  
  
 \(이 언어 기능에는 Windows 런타임에만 적용되는 설명이 없습니다.\)  
  
### 요구 사항  
 컴파일러 옵션: **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **설명**  
  
 \(이 언어 기능에는 공용 언어 런타임에만 적용되는 설명이 없습니다.\)  
  
### 요구 사항  
 컴파일러 옵션: **\/clr**  
  
### 예제  
 **예제**  
  
 다음 코드 예제에서는 인터페이스 시계 함수의 동작을 정의하는 방법을 보여줍니다.  
  
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
  
 **Output**  
  
  **IN 함수 3**  
 **IN 함수 2**  
 **IN 함수 1**  
 **8**  
 **OnClick: 7, 3.14159**  
 **IN 함수 1** **예제**  
  
 다음 코드 예제에서는 시그니처가 동일한 선언에서 여러 인터페이스 및 인터페이스 클래스에 의해 사용되는 위치 기능을 구현하는 두 가지 보여줍니다.  
  
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
  
## 참고 항목  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)