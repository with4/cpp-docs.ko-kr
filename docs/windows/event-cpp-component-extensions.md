---
title: "event  (C++ Component Extensions) | Microsoft Docs"
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
  - "event"
  - "event_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "event keyword [C++]"
ms.assetid: c4998e42-883c-4419-bbf4-36cdc979dd27
caps.latest.revision: 34
caps.handback.revision: 32
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# event  (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`event` 키워드는 특정 상황이 발생했음을 등록된 구독자\(*이벤트 처리기*\)에 알리는 *이벤트*를 선언합니다.  
  
## 모든 런타임  
 C\+\+\/CX는 *이벤트 멤버* 또는 *이벤트 블록* 선언을 지원합니다.  이벤트 멤버는 이벤트 블록을 선언하기 위한 약칭입니다.  기본적으로는 이벤트 멤버는 이벤트 블록에서 명시적으로 선언된 `add()`, `remove()` 및 `raise()` 함수를 선언합니다.  이벤트 멤버의 함수를 사용자 지정하려면 대신에 이벤트 블록을 선언하고 필요한 함수를 재정의합니다.  
  
 **구문**  
  
```  
  
// event data member  
modifier event delegate^ event_name;     
  
// event block  
modifier event delegate^ event_name   
{  
   modifier return_value add(delegate^ name);  
   modifier void remove(delegate^ name);  
   modifier void raise(parameters);  
}  
```  
  
 **매개 변수**  
  
 *modifier*  
 이벤트 선언 또는 이벤트 접근자 메서드에 사용할 수 있는 한정자입니다.  가능한 값은 `static`와 `virtual`입니다.  
  
 *대리자*  
 이벤트 처리기가 일치해야 하는 서명을 가진 [대리자](../windows/delegate-cpp-component-extensions.md)입니다.  
  
 *event\_name*  
 이벤트의 이름입니다.  
  
 *return\_value*  
 이벤트 접근자 메서드의 반환 값입니다.  확인할 수 있으려면 반환 형식이 `void`여야 합니다.  
  
 *parameters*  
 \(선택 사항\) *delegate* 매개 변수의 서명과 일치하는 `raise` 메서드에 대한 매개 변수입니다.  
  
 **설명**  
  
 이벤트는 대리자와 이벤트 트리거에 응답하는 멤버 함수\(이벤트 처리기\) 간의 연결이고 이를 통해 모든 클래스의 클라이언트가 기본 대리자의 서명 및 반환 형식을 준수하는 메서드를 등록할 수 있습니다.  
  
 이벤트 선언에는 다음 두 가지 종류가 있습니다.  
  
 *이벤트 데이터 멤버*  
 컴파일러에서는 대리자 형식의 멤버 형식으로 이벤트에 대한 저장소를 자동으로 만들고 내부 `add()`, `remove()` 및 `raise()` 멤버 함수를 만듭니다.  이벤트 데이터 멤버는 클래스 내에 선언되어야 합니다.  대리자의 반환 형식은 이벤트 처리기의 반환 형식과 일치해야 합니다.  
  
 *이벤트 블록*  
 이벤트 블록을 사용하여 `add()`, `remove()` 및 `raise()` 메서드의 동작을 명시적으로 선언 및 사용자 지정할 수 있습니다.  
  
 `operators+=` 및 `operator-=`를 사용하여 이벤트 처리기를 추가 및 제거하거나 `add()` 및 `remove()` 메서드를 명시적으로 호출할 수 있습니다.  
  
 `event`는 상황에 맞는 키워드입니다. 자세한 내용은 [상황에 맞는 키워드](../windows/context-sensitive-keywords-cpp-component-extensions.md)를 참조하세요.  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
  
### 설명  
 자세한 내용은 [이벤트\(C\+\+\/CX\)](http://msdn.microsoft.com/library/windows/apps/hh755799.aspx)를 참조하세요.  
  
 이벤트 처리기를 추가하고 나서 제거하려면 추가 작업에서 반환되는 EventRegistrationToken 구조체를 저장해야 합니다.  그다음에 제거 작업에서 저장된 EventRegistrationToken 구조체를 사용하여 제거할 이벤트 처리기를 식별해야 합니다.  
  
### 요구 사항  
 컴파일러 옵션: **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 `event` 키워드를 통해 이벤트를 선언할 수 있습니다.  이벤트는 특정 상황이 발생할 때 클래스가 알림을 제공하는 한 가지 방법입니다.  
  
 **구문**  
  
```  
  
// event data member  
modifier event delegate^ event_name;   
  
// event block  
modifier event delegate^ event_name   
{  
   modifier return_value add(delegate^ name);  
   modifier void remove(delegate^ name);  
   modifier void raise(parameters);  
}  
```  
  
 **매개 변수**  
  
 *modifier*  
 이벤트 선언 또는 이벤트 접근자 메서드에 사용할 수 있는 한정자입니다.  가능한 값은 `static`와 `virtual`입니다.  
  
 *대리자*  
 이벤트 처리기가 일치해야 하는 서명을 가진 [대리자](../windows/delegate-cpp-component-extensions.md)입니다.  
  
 *event\_name*  
 이벤트의 이름입니다.  
  
 *return\_value*  
 이벤트 접근자 메서드의 반환 값입니다.  확인할 수 있으려면 반환 형식이 `void`여야 합니다.  
  
 *parameters*  
 \(선택 사항\) *delegate* 매개 변수의 서명과 일치하는 `raise` 메서드에 대한 매개 변수입니다.  
  
 **설명**  
  
 이벤트는 대리자와 이벤트 트리거에 응답하는 멤버 함수\(이벤트 처리기\) 간의 연결이고 이를 통해 모든 클래스의 클라이언트가 기본 대리자의 서명 및 반환 형식을 준수하는 메서드를 등록할 수 있습니다.  
  
 대리자에는 코드에서 이벤트가 발생했음을 나타낼 때 호출될 하나 이상의 연결된 메서드가 있을 수 있습니다.  한 프로그램의 이벤트를 .NET Framework 공용 언어 런타임을 대상으로 하는 다른 프로그램에서 사용 가능하게 설정할 수 있습니다.  샘플에 대해서는 [다른 어셈블리에 정의된 발생](../misc/how-to-raise-events-defined-in-a-different-assembly.md)을 참조하세요.  
  
 이벤트 선언에는 다음 두 가지 종류가 있습니다.  
  
 *이벤트 데이터 멤버*  
 이벤트에 대한 저장소는 컴파일러에 의해 데이터 멤버 이벤트에 대해 대리자 형식의 멤버 형식으로 생성됩니다.  이벤트 데이터 멤버는 클래스 내에 선언되어야 합니다.  이를 trivial 이벤트라고도 합니다\(아래 코드 샘플 참조\).  
  
 *이벤트 블록*  
 이벤트 블록을 통해 add, remove 및 raise 메서드를 구현하여 add, remove 및 raise 메서드의 동작을 사용자 지정할 수 있습니다.  add, remove 및 raise 메서드의 서명은 대리자의 서명과 일치해야 합니다.  이벤트 블록은 데이터 멤버가 아니며 데이터 멤버로 사용하면 컴파일러 오류가 발생합니다.  샘플에 대해서는 [이벤트 접근자 메서드 정의](../misc/how-to-define-event-accessor-methods.md)를 참조하세요.  
  
 이벤트 처리기의 반환 형식은 대리자의 반환 형식과 일치해야 합니다.  
  
 .NET Framework에서 데이터 멤버를 메서드\(즉, 해당 대리자의 `Invoke` 메서드\) 자체인 것처럼 취급할 수 있습니다.  관리되는 이벤트 데이터 멤버를 선언하기 위한 대리자 형식을 미리 정의해야 합니다.  반면에 관리되는 이벤트 메서드는 해당 관리되는 대리자\(이미 정의되지 않은 경우\)를 암시적으로 정의합니다.  예제를 보려면 이 항목의 끝 부분에 있는 코드 샘플을 참조하세요.  
  
 관리되는 이벤트를 선언할 때 \+\= 및 \-\= 연산자를 사용하여 이벤트 처리기가 추가되거나 제거되는 경우 호출될 add 및 remove 접근자를 지정할 수 있습니다.  add, remove 및 raise 메서드는 명시적으로 호출할 수 있습니다.  
  
 Visual C\+\+에서 이벤트를 만들고 사용하려면 다음 단계를 수행해야 합니다.  
  
1.  대리자를 만들거나 식별합니다.  고유한 이벤트를 정의할 경우 `event` 키워드와 함께 사용할 대리자가 있는지 확인해야 합니다.  예를 들어 이벤트가 미리 정의되어 있으면 .NET Framework에서 이벤트 소비자는 대리자의 이름만 알면 됩니다.  
  
2.  다음을 포함하는 클래스를 만듭니다.  
  
    -   대리자에서 생성된 이벤트.  
  
    -   \(선택 사항\) `event` 키워드를 통해 선언된 대리자의 인스턴스가 있는지 확인하는 메서드.  이외에는 이 논리가 이벤트를 실행하는 코드에 배치되어야 합니다.  
  
    -   이벤트를 호출하는 메서드.  이들 메서드는 일부 기본 클래스 기능의 재정의일 수 있습니다.  
  
     이 클래스는 이벤트를 정의합니다.  
  
3.  메서드를 이벤트에 연결하는 하나 이상의 클래스를 정의합니다.  이러한 각 클래스는 하나 이상의 메서드를 기본 클래스의 이벤트와 연결합니다.  
  
4.  이벤트를 사용합니다.  
  
    -   이벤트 선언을 포함하는 클래스의 개체를 만듭니다.  
  
    -   이벤트 정의를 포함하는 클래스의 개체를 만듭니다.  
  
 [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)] 이벤트에 대한 자세한 내용은 다음을 참조하세요.  
  
-   [인터페이스의 이벤트](../dotnet/how-to-use-events-in-cpp-cli.md)  
  
-   [add, remove 및 raise 메서드의 기본 액세스 재정의](../misc/how-to-override-default-access-of-add-remove-and-raise-methods.md)  
  
-   [이벤트에 대한 여러 처리기](../misc/how-to-add-multiple-handlers-to-events.md)  
  
-   [관리되는 가상 이벤트](../misc/how-to-implement-managed-virtual-events.md)  
  
-   [이벤트 접근자 메서드](../misc/how-to-define-event-accessor-methods.md)  
  
-   [정적 이벤트](../misc/how-to-define-and-use-static-events.md)  
  
-   [다른 어셈블리에 정의된 이벤트 발생](../misc/how-to-raise-events-defined-in-a-different-assembly.md)  
  
-   [추상 이벤트](../misc/how-to-implement-abstract-events.md)  
  
### 요구 사항  
 컴파일러 옵션: **\/clr**  
  
### 예  
 **예제**  
  
 다음 코드 예제에서는 대리자, 이벤트 및 이벤트 처리기의 쌍을 선언하고, 이벤트 처리기를 구독\(추가\)하고, 이벤트 처리기를 호출하고, 이벤트 처리기를 구독 취소\(제거\)하는 방법을 보여 줍니다.  
  
```  
// mcppv2_events.cpp  
// compile with: /clr  
using namespace System;  
  
// declare delegates  
delegate void ClickEventHandler(int, double);  
delegate void DblClickEventHandler(String^);  
  
// class that defines events  
ref class EventSource {  
public:  
   event ClickEventHandler^ OnClick;   // declare the event OnClick  
   event DblClickEventHandler^ OnDblClick;   // declare OnDblClick  
  
   void FireEvents() {  
      // raises events  
      OnClick(7, 3.14159);  
      OnDblClick("Hello");  
   }  
};  
  
// class that defines methods that will called when event occurs  
ref class EventReceiver {  
public:  
   void OnMyClick(int i, double d) {  
      Console::WriteLine("OnClick: {0}, {1}", i, d);  
   }  
  
   void OnMyDblClick(String^ str) {  
      Console::WriteLine("OnDblClick: {0}", str);  
   }  
};  
  
int main() {  
   EventSource ^ MyEventSource = gcnew EventSource();  
   EventReceiver^ MyEventReceiver = gcnew EventReceiver();  
  
   // hook handler to event  
   MyEventSource->OnClick += gcnew ClickEventHandler(MyEventReceiver, &EventReceiver::OnMyClick);  
   MyEventSource->OnDblClick += gcnew DblClickEventHandler(MyEventReceiver, &EventReceiver::OnMyDblClick);  
  
   // invoke events  
   MyEventSource->FireEvents();  
  
   // unhook handler to event  
   MyEventSource->OnClick -= gcnew ClickEventHandler(MyEventReceiver, &EventReceiver::OnMyClick);  
   MyEventSource->OnDblClick -= gcnew DblClickEventHandler(MyEventReceiver, &EventReceiver::OnMyDblClick);  
}  
```  
  
 **출력**  
  
  **OnClick: 7, 3.14159**  
 **OnDblClick: Hello** **예제**  
  
 다음 코드 예제에서는 trivial 이벤트의 `raise` 메서드를 생성하는 데 사용되는 논리를 보여 줍니다. 이벤트에 하나 이상의 구독자가 있는 경우 `raise` 메서드를 암시적으로 또는 명시적으로 호출하면 대리자가 호출됩니다.  대리자의 반환 형식이 `void`가 아닌 경우 및 0 이벤트 구독자가 있는 경우 `raise` 메서드는 대리자 형식의 기본값을 반환합니다.  이벤트 구독자가 없는 경우 `raise` 메서드를 호출하면 단순히 반환하고 예외가 발생하지 않습니다.  대리자 반환 형식이 `void`가 아니면 대리자 형식이 반환됩니다.  
  
```  
// trivial_events.cpp  
// compile with: /clr /c  
using namespace System;  
public delegate int Del();  
public ref struct C {  
   int i;  
   event Del^ MyEvent;  
  
   void FireEvent() {  
      i = MyEvent();  
   }  
};  
  
ref struct EventReceiver {  
   int OnMyClick() { return 0; }  
};  
  
int main() {  
   C c;  
   c.i = 687;  
  
   c.FireEvent();  
   Console::WriteLine(c.i);  
   c.i = 688;  
  
   EventReceiver^ MyEventReceiver = gcnew EventReceiver();  
   c.MyEvent += gcnew Del(MyEventReceiver, &EventReceiver::OnMyClick);  
   Console::WriteLine(c.i);     
}  
```  
  
 **출력**  
  
  **0**  
 **688**   
## 참고 항목  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)