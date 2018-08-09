---
title: event (c + + 구성 요소 확장) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event
- event_cpp
dev_langs:
- C++
helpviewer_keywords:
- event keyword [C++]
ms.assetid: c4998e42-883c-4419-bbf4-36cdc979dd27
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6b3ee48394eede37873ce074c275290307215815
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39649138"
---
# <a name="event--c-component-extensions"></a>event(C++ 구성 요소 확장)
**이벤트** 키워드로 선언 된는 *이벤트*에 등록 된 구독자에 게 알리는 (*이벤트 처리기*) 특정 상황이 발생 합니다.  
  
## <a name="all-runtimes"></a>모든 런타임  
 C + + /cli CX 선언 하도록 지원를 *이벤트 멤버* 요소나 *이벤트 블록*합니다. 이벤트 멤버는 이벤트 블록을 선언하기 위한 약칭입니다. 기본적으로는 이벤트 멤버는 이벤트 블록에서 명시적으로 선언된 `add()`, `remove()` 및 `raise()` 함수를 선언합니다. 이벤트 멤버의 함수를 사용자 지정하려면 대신에 이벤트 블록을 선언하고 필요한 함수를 재정의합니다.  
  
### <a name="syntax"></a>구문
  
```cpp  
// event data member  
modifiereventdelegate^ event_name;     
  
// event block  
modifiereventdelegate^ event_name   
{  
   modifierreturn_valueadd(delegate^ name);  
   modifier void remove(delegate^ name);  
   modifier void raise(parameters);  
}  
```  
  
### <a name="parameters"></a>매개 변수
 *한정자*  
 이벤트 선언 또는 이벤트 접근자 메서드에 사용할 수 있는 한정자입니다.  가능한 값은 **정적** 하 고 **가상**합니다.  
  
 *delegate*  
 합니다 [대리자](../windows/delegate-cpp-component-extensions.md), 시그니처를 가진 이벤트 처리기가 일치 해야 합니다.  
  
 *event_name*  
 이벤트의 이름입니다.  
  
 *return_value*  
 이벤트 접근자 메서드의 반환 값입니다.  반환 형식을 확인할 수 있어야 **void**합니다.  
  
 *parameters*  
 (선택 사항) 에 대 한 매개 변수를 `raise` 의 서명과 일치 하는 메서드를 *대리자* 매개 변수입니다.  
  
### <a name="remarks"></a>설명
  
 이벤트는 대리자와 이벤트 트리거에 응답하는 멤버 함수(이벤트 처리기) 간의 연결이고 이를 통해 모든 클래스의 클라이언트가 기본 대리자의 서명 및 반환 형식을 준수하는 메서드를 등록할 수 있습니다.  
  
 이벤트 선언에는 다음 두 가지 종류가 있습니다.  
  
 *이벤트 데이터 멤버*  
 컴파일러에서는 대리자 형식의 멤버 형식으로 이벤트에 대한 저장소를 자동으로 만들고 내부 `add()`, `remove()` 및 `raise()` 멤버 함수를 만듭니다. 이벤트 데이터 멤버는 클래스 내에 선언되어야 합니다. 대리자의 반환 형식은 이벤트 처리기의 반환 형식과 일치해야 합니다.  
  
 *이벤트 블록*  
 이벤트 블록을 사용하여 `add()`, `remove()` 및 `raise()` 메서드의 동작을 명시적으로 선언 및 사용자 지정할 수 있습니다.  
  
 사용할 수 있습니다 **연산자 + =** 및 **-= 연산자** 추가 및 제거할 이벤트 처리기 또는 호출을 `add()` 및 `remove()` 메서드 명시적으로.  
  
 **이벤트** 상황에 맞는 키워드는 참조 [상황에 맞는 키워드](../windows/context-sensitive-keywords-cpp-component-extensions.md) 자세한 내용은 합니다.  
  
## <a name="windows-runtime"></a>Windows 런타임  
  
### <a name="remarks"></a>설명  
 자세한 내용은 [이벤트 (C + + /cli CX)](http://msdn.microsoft.com/library/windows/apps/hh755799.aspx)합니다.  
  
 이벤트 처리기를 추가하고 나서 제거하려면 추가 작업에서 반환되는 EventRegistrationToken 구조체를 저장해야 합니다. 그다음에 제거 작업에서 저장된 EventRegistrationToken 구조체를 사용하여 제거할 이벤트 처리기를 식별해야 합니다.  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: `/ZW`  
  
## <a name="common-language-runtime"></a>공용 언어 런타임 
 합니다 **이벤트** 키워드를 사용 하면 이벤트를 선언 합니다. 이벤트는 특정 상황이 발생할 때 클래스가 알림을 제공하는 한 가지 방법입니다.  
  
### <a name="syntax"></a>구문
  
```cpp  
// event data member  
modifiereventdelegate^ event_name;   
  
// event block  
modifiereventdelegate^ event_name   
{  
   modifierreturn_valueadd(delegate^ name);  
   modifier void remove(delegate^ name);  
   modifier void raise(parameters);  
}  
```  
  
### <a name="parameters"></a>매개 변수
 *한정자*  
 이벤트 선언 또는 이벤트 접근자 메서드에 사용할 수 있는 한정자입니다.  가능한 값은 **정적** 하 고 **가상**합니다.  
  
 *delegate*  
 합니다 [대리자](../windows/delegate-cpp-component-extensions.md), 시그니처를 가진 이벤트 처리기가 일치 해야 합니다.  
  
 *event_name*  
 이벤트의 이름입니다.  
  
 *return_value*  
 이벤트 접근자 메서드의 반환 값입니다.  반환 형식을 확인할 수 있어야 **void**합니다.  
  
 *parameters*  
 (선택 사항) 에 대 한 매개 변수를 `raise` 의 서명과 일치 하는 메서드를 *대리자* 매개 변수입니다.  
  
### <a name="remarks"></a>설명
 이벤트는 대리자와 이벤트 트리거에 응답하는 멤버 함수(이벤트 처리기) 간의 연결이고 이를 통해 모든 클래스의 클라이언트가 기본 대리자의 서명 및 반환 형식을 준수하는 메서드를 등록할 수 있습니다.  
  
 대리자에는 코드에서 이벤트가 발생했음을 나타낼 때 호출될 하나 이상의 연결된 메서드가 있을 수 있습니다. 한 프로그램의 이벤트를 .NET Framework 공용 언어 런타임을 대상으로 하는 다른 프로그램에서 사용 가능하게 설정할 수 있습니다.  
  
 이벤트 선언에는 다음 두 가지 종류가 있습니다.  
  
 *이벤트 데이터 멤버*  
 이벤트에 대한 저장소는 컴파일러에 의해 데이터 멤버 이벤트에 대해 대리자 형식의 멤버 형식으로 생성됩니다.  이벤트 데이터 멤버는 클래스 내에 선언되어야 합니다. 이를 trivial 이벤트라고도 합니다(아래 코드 샘플 참조).  
  
 *이벤트 블록*  
 이벤트 블록을 통해 add, remove 및 raise 메서드를 구현하여 add, remove 및 raise 메서드의 동작을 사용자 지정할 수 있습니다. add, remove 및 raise 메서드의 서명은 대리자의 서명과 일치해야 합니다.  이벤트 블록은 데이터 멤버가 아니며 데이터 멤버로 사용하면 컴파일러 오류가 발생합니다. 
  
 이벤트 처리기의 반환 형식은 대리자의 반환 형식과 일치해야 합니다.  
  
 .NET Framework에서 데이터 멤버를 메서드(즉, 해당 대리자의 `Invoke` 메서드) 자체인 것처럼 취급할 수 있습니다. 관리되는 이벤트 데이터 멤버를 선언하기 위한 대리자 형식을 미리 정의해야 합니다. 반면에 관리되는 이벤트 메서드는 해당 관리되는 대리자(이미 정의되지 않은 경우)를 암시적으로 정의합니다.  예제를 보려면 이 항목의 끝 부분에 있는 코드 샘플을 참조하세요.  
  
 관리되는 이벤트를 선언할 때 += 및 -= 연산자를 사용하여 이벤트 처리기가 추가되거나 제거되는 경우 호출될 add 및 remove 접근자를 지정할 수 있습니다. add, remove 및 raise 메서드는 명시적으로 호출할 수 있습니다.  
  
 Visual C++에서 이벤트를 만들고 사용하려면 다음 단계를 수행해야 합니다.  
  
1.  대리자를 만들거나 식별합니다. 사용자 고유의 이벤트를 정의 하는 경우 확인 해야 합니다도 대리자를 사용 하는 합니다 **이벤트** 키워드입니다. 예를 들어 이벤트가 미리 정의되어 있으면 .NET Framework에서 이벤트 소비자는 대리자의 이름만 알면 됩니다.  
  
2.  다음을 포함하는 클래스를 만듭니다.  
  
    -   대리자에서 생성된 이벤트.  
  
    -   (선택 사항) 로 선언 된 대리자의 인스턴스 하는 확인 하는 메서드를 **이벤트** 키워드 존재 합니다. 이외에는 이 논리가 이벤트를 실행하는 코드에 배치되어야 합니다.  
  
    -   이벤트를 호출하는 메서드. 이들 메서드는 일부 기본 클래스 기능의 재정의일 수 있습니다.  
  
     이 클래스는 이벤트를 정의합니다.  
  
3.  메서드를 이벤트에 연결하는 하나 이상의 클래스를 정의합니다. 이러한 각 클래스는 하나 이상의 메서드를 기본 클래스의 이벤트와 연결합니다.  
  
4.  이벤트를 사용합니다.  
  
    -   이벤트 선언을 포함하는 클래스의 개체를 만듭니다.  
  
    -   이벤트 정의를 포함하는 클래스의 개체를 만듭니다.  
  
 자세한 내용은 C + + /cli CLI 이벤트를 참조 하세요.  
  
-   [인터페이스의 이벤트](../dotnet/how-to-use-events-in-cpp-cli.md)  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: `/clr`  
  
### <a name="examples"></a>예제  

 다음 코드 예제에서는 대리자, 이벤트 및 이벤트 처리기의 쌍을 선언하고, 이벤트 처리기를 구독(추가)하고, 이벤트 처리기를 호출하고, 이벤트 처리기를 구독 취소(제거)하는 방법을 보여 줍니다.  
  
```cpp  
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
  
```Output  
OnClick: 7, 3.14159  
  
OnDblClick: Hello  
```  
  
 다음 코드 예제에서는 trivial 이벤트의 `raise` 메서드를 생성하는 데 사용되는 논리를 보여 줍니다. 이벤트에 하나 이상의 구독자가 있는 경우 `raise` 메서드를 암시적으로 또는 명시적으로 호출하면 대리자가 호출됩니다. 대리자의 반환 형식이 없으면 **void** 0 이벤트 구독자가 있는 경우 및는 `raise` 메서드는 대리자 형식의 기본값을 반환 합니다. 이벤트 구독자가 없는 경우 `raise` 메서드를 호출하면 단순히 반환하고 예외가 발생하지 않습니다. 대리자 반환 형식이 아닙니다 **void**, 대리자 형식이 반환 됩니다.  
  
```cpp  
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
  
```Output  
0  
  
688  
```  
  
## <a name="see-also"></a>참고 항목  
 [런타임 플랫폼용 구성 요소 확장](../windows/component-extensions-for-runtime-platforms.md)