---
title: "__event | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__event_cpp"
  - "__event"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__event 키워드[C++]"
  - "이벤트[C++], __event"
ms.assetid: d3019b3e-722e-48df-8536-c05878461f9e
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# __event
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이벤트를 선언합니다.  
  
## 구문  
  
```  
  
      __event   
      method-declarator  
      ;  
__event __interface interface-specifier;  
__event member-declarator;  
```  
  
## 설명  
 `__event` 키워드는 메서드 선언, 인터페이스 선언 또는 데이터 멤버 선언에 적용할 수 있습니다.  하지만 `__event` 키워드를 사용하여 중첩된 클래스의 멤버를 한정할 수는 없습니다.  
  
 이벤트 소스 및 수신기가 네이티브 C\+\+ 또는 COM이거나 관리되는지\(.NET Framework\)에 따라 다음 구문을 이벤트로 사용할 수 있습니다.  
  
|네이티브 C\+\+|COM|관리됨\(.NET Framework\)|  
|----------------|---------|---------------------------|  
|메서드|—|메서드|  
|—|인터페이스|—|  
|—|—|데이터 멤버|  
  
 이벤트 수신기에서 [\_\_hook](../cpp/hook.md)를 사용하여 처리기 메서드를 이벤트 메서드와 연결할 수 있습니다.  `__event` 키워드를 사용하여 이벤트를 만든 후에는 이벤트가 호출될 때 이후에 해당 이벤트에 후크된 모든 이벤트 처리기가 호출됩니다.  
  
 `__event` 메서드 선언에는 정의가 있을 수 없습니다. 정의는 암시적으로 생성되므로 이벤트 메서드는 일반 메서드인 것처럼 호출될 수 있습니다.  
  
> [!NOTE]
>  템플릿 기반 클래스 또는 구조체에 event를 포함시킬 수 없습니다.  
  
## 네이티브 이벤트  
 네이티브 이벤트는 메서드입니다.  반환 형식은 일반적으로 `HRESULT` 또는 `void`이지만 `enum`을 비롯한 모든 정수 계열 형식일 수 있습니다.  이벤트가 정수 계열 반환 형식을 사용하는 경우 이벤트 처리기가 0이 아닌 값을 반환할 때 오류 조건이 정의됩니다. 이 경우 발생하는 이벤트는 다른 대리자를 호출합니다.  
  
```  
// Examples of native C++ events:  
__event void OnDblClick();  
__event HRESULT OnClick(int* b, char* s);  
```  
  
 샘플 코드는 [네이티브 C\+\+에서 이벤트 처리](../cpp/event-handling-in-native-cpp.md)를 참조하십시오.  
  
## COM 이벤트  
 COM 이벤트는 인터페이스입니다.  이벤트 소스 인터페이스에 있는 메서드의 매개 변수는 **out** 매개 변수가 멀티캐스팅 시 유용하지 않기 때문에 **in** 매개 변수여야 합니다\(그러나 엄격하게 적용되지는 않음\).  **out** 매개 변수를 사용하는 경우 수준 1 경고가 발행됩니다.  
  
 반환 형식은 일반적으로 `HRESULT` 또는 `void`이지만 `enum`을 비롯한 모든 정수 계열 형식일 수 있습니다.  이벤트가 정수 계열 반환 형식을 사용하고 이벤트 처리기가 0이 아닌 값을 반환하는 경우는 오류 조건이며 이 경우 발생하는 이벤트가 다른 대리자에 대한 호출을 중단합니다.  컴파일러는 이벤트 소스 인터페이스를 생성된 IDL에서 자동으로 [source](../windows/source-cpp.md)로 표시합니다.  
  
 COM 이벤트 소스의 경우 [\_\_Interface](../cpp/interface.md) 키워드가 `__event` 뒤에 항상 필요합니다.  
  
```  
// Example of a COM event:  
__event __interface IEvent1;  
```  
  
 샘플 코드는 [COM에서 이벤트 처리](../cpp/event-handling-in-com.md)를 참조하십시오.  
  
## 관리되는 이벤트  
 새 구문의 이벤트 코딩에 대한 자세한 내용은 [event](../windows/event-cpp-component-extensions.md)를 참조하십시오.  
  
 관리되는 이벤트는 데이터 멤버 또는 메서드입니다.  이벤트와 함께 사용되는 경우 대리자의 반환 형식은 [공용 언어 사양](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md)을 준수해야 합니다.  이벤트 처리기의 반환 형식은 대리자의 반환 형식과 일치해야 합니다.  대리자에 대한 자세한 내용은 [\_\_delegate](../misc/delegate.md)를 참조하십시오.  관리되는 이벤트가 데이터 멤버인 경우 그 형식은 대리자에 대한 포인터여야 합니다.  
  
 .NET Framework에서 데이터 멤버를 메서드\(즉, 해당 대리자의 `Invoke` 메서드\) 자체인 것처럼 취급할 수 있습니다.  관리되는 이벤트 데이터 멤버를 선언하기 위한 대리자 형식을 미리 정의해야 합니다.  반면에 관리되는 이벤트 메서드는 해당 관리되는 대리자\(이미 정의되지 않은 경우\)를 암시적으로 정의합니다.  예를 들어 `OnClick`과 같은 이벤트 값을 다음과 같이 이벤트로 선언할 수 있습니다.  
  
```  
// Examples of managed events:  
__event ClickEventHandler* OnClick;  // data member as event  
__event void OnClick(String* s);  // method as event  
```  
  
 관리되는 이벤트를 암시적으로 선언할 때 이벤트 처리기가 추가되거나 제거되는 경우 호출될 add 및 remove 접근자를 지정할 수 있습니다.  클래스 외부에서 이벤트를 호출하는\(발생시키는\) 메서드를 정의할 수도 있습니다.  
  
## 예제: 네이티브 이벤트  
  
```  
// EventHandling_Native_Event.cpp  
// compile with: /c  
[event_source(native)]  
class CSource {  
public:  
   __event void MyEvent(int nValue);  
};  
```  
  
## 예제: COM 이벤트  
  
```  
// EventHandling_COM_Event.cpp  
// compile with: /c  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
  
[ module(dll, name="EventSource", uuid="6E46B59E-89C3-4c15-A6D8-B8A1CEC98830") ];  
  
[ dual, uuid("00000000-0000-0000-0000-000000000002") ]  
__interface IEventSource {  
   [id(1)] HRESULT MyEvent();  
};  
 [ coclass, uuid("00000000-0000-0000-0000-000000000003"),  event_source(com) ]  
class CSource : public IEventSource {  
public:  
   __event __interface IEventSource;  
   HRESULT FireEvent() {  
      __raise MyEvent();  
      return S_OK;  
   }  
};  
```  
  
## 예제: 관리되는 이벤트  
  
```  
// EventHandling_Managed_Event.cpp  
// compile with: /clr:oldSyntax /c  
using namespace System;  
[event_source(managed)]  
public __gc class CPSource {  
  
public:  
   __event void MyEvent(Int16 nValue);  
};  
```  
  
 이벤트에 특성을 적용할 때 특성이 생성된 메서드나 생성된 대리자의 Invoke 메서드에 적용되도록 지정할 수 있습니다.  기본값\(`event:`\)은 특성을 이벤트에 적용하는 것입니다.  
  
```  
// EventHandling_Managed_Event_2.cpp  
// compile with: /clr:oldSyntax /c  
using namespace System;  
[attribute(All, AllowMultiple=true)]  
public __gc class Attr {};  
  
public __delegate void D();  
  
public __gc class X {  
public:  
   [method:Attr] __event D* E;  
   [returnvalue:Attr] __event void noE();  
};  
```  
  
## 참고 항목  
 [C\+\+ 키워드](../cpp/keywords-cpp.md)   
 [이벤트 처리](../cpp/event-handling.md)   
 [event\_source](../windows/event-source.md)   
 [event\_receiver](../windows/event-receiver.md)   
 [\_\_hook](../cpp/hook.md)   
 [\_\_unhook](../cpp/unhook.md)   
 [\_\_raise](../cpp/raise.md)