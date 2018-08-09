---
title: 인터페이스 클래스 (c + + 구성 요소 확장) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- interface_CPP
dev_langs:
- C++
helpviewer_keywords:
- interface class keyword
- interface struct keyword
ms.assetid: 3ccea701-f50b-4da7-ad6b-f0ee1203e2b9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cda56029b94d2c4be55ce133d96adb76663491ae
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40012835"
---
# <a name="interface-class--c-component-extensions"></a>interface 클래스(C++ 구성 요소 확장)
인터페이스를 선언합니다.  네이티브 인터페이스에 대 한 내용은 참조 하세요 [__interface](../cpp/interface.md)합니다.  
  
## <a name="all-runtimes"></a>모든 런타임  

### <a name="syntax"></a>구문  
  
```cpp  
interface_access  
interface class  
 name :  inherit_accessbase_interface{};interface_accessinterface structname :  inherit_accessbase_interface{};  
```  
  
### <a name="parameters"></a>매개 변수  
 *interface_access*  
 어셈블리 외부에서 인터페이스의 접근성입니다.  가능한 값은 **공개** 하 고 **개인**합니다.  **개인** 가 기본값입니다. 중첩 된 인터페이스를 사용할 수 없습니다는 *interface_access* 지정자입니다.  
  
 *name*  
 인터페이스의 이름입니다.  
  
 *inherit_access*  
 액세스 가능성 *base_interface*합니다.  수만 내게 필요한 옵션을 기본 인터페이스에 대 한 **공용** (기본값).  
  
 *base_interface* (선택 사항)  
 인터페이스에 대 한 기본 인터페이스 *이름을*입니다.  
  
### <a name="remarks"></a>설명  
  
 **인터페이스 구조체** 같습니다 **인터페이스 클래스**합니다.  
  
 인터페이스에는 함수, 이벤트 및 속성에 대 한 선언을 포함할 수 있습니다.  모든 인터페이스 멤버는 public 액세스 가능성을 갖습니다. 인터페이스에는 정적 데이터 멤버, 함수, 이벤트 및 속성을 포함할 수도 있습니다 및 인터페이스에서 이러한 정적 멤버를 정의 해야 합니다.  
  
 인터페이스는 클래스를 구현할 수 있습니다 하는 방법을 정의 합니다. 인터페이스 클래스 아니며 클래스 이름만 인터페이스를 구현할 수 있습니다. 클래스 인터페이스에서 선언 된 함수를 정의 하는 경우 재정의 되지 않은 함수 구현 됩니다. 따라서 이름 조회는 인터페이스 멤버를 포함 되지 않습니다.  
  
 클래스 또는 구조체는 인터페이스에서 파생 되는 인터페이스의 모든 멤버를 구현 해야 합니다. 인터페이스를 구현 하는 경우 *이름을* 의 인터페이스를 구현 해야 합니다 `base_interface` 목록입니다.  
  
 자세한 내용은 다음을 참조하세요.  
  
-   [인터페이스 정적 생성자](../dotnet/how-to-define-an-interface-static-constructor-cpp-cli.md)  
  
-   [제네릭 인터페이스(Visual C++)](../windows/generic-interfaces-visual-cpp.md)  
  
 다른 CLR 형식에 대 한 자세한 내용은 [클래스 및 구조체](../windows/classes-and-structs-cpp-component-extensions.md)합니다.  
  
 형식을 사용 하 여 인터페이스 이면 컴파일 시간에 감지할 수 있습니다 `__is_interface_class(type)`합니다. 자세한 내용은 [형식 특성에 대 한 컴파일러 지원](../windows/compiler-support-for-type-traits-cpp-component-extensions.md)합니다.  
  
 개발 환경에서에서 얻을 수 있습니다 F1 도움말이 키워드 이러한 키워드를 강조 표시 하 여 (`interface class`예를 들어) F1 키를 누릅니다.  
  
## <a name="windows-runtime"></a>Windows 런타임  
### <a name="remarks"></a>설명 
  
 (이 언어 기능에는 Windows 런타임에만 적용되는 설명이 없습니다.)  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: `/ZW`  
  
## <a name="common-language-runtime"></a>공용 언어 런타임 
### <a name="remarks"></a>설명
  
 (이 언어 기능에는 공용 언어 런타임에만 적용되는 설명이 없습니다.)  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: `/clr`  
  
### <a name="examples"></a>예제  
  
 다음 코드 예제에서는 인터페이스 클록 함수의 동작을 정의할 수 있습니다 하는 방법을 보여 줍니다.  
  
```cpp  
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
  
```Output  
in Function_3  
  
in Function_2  
  
in Function_1  
  
8  
  
OnClick: 7, 3.14159  
  
in Function_1  
```  
  
 다음 코드 샘플에는 여러 인터페이스 및 해당 인터페이스를 클래스에 의해 사용 되는 위치를 선언 합니다. 동일한 서명을 사용 하 여 함수를 구현 하는 두 가지 방법 보여 줍니다.  
  
```cpp  
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