---
title: __event | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __event_cpp
- __event
dev_langs:
- C++
helpviewer_keywords:
- __event keyword [C++]
- events [C++], __event
ms.assetid: d3019b3e-722e-48df-8536-c05878461f9e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: abfda38c6c35c3e7172b187c89fa78bed5ee7616
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37944518"
---
# <a name="event"></a>__event
이벤트를 선언합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
__event method-declarator;  
__event __interface interface-specifier;  
__event member-declarator;  
```  
  
## <a name="remarks"></a>설명  
 키워드 **__event** 메서드 선언, 인터페이스 선언 또는 데이터 멤버 선언에 적용할 수 있습니다. 그러나 사용할 수 없습니다 합니다 **__event** 중첩된 된 클래스의 멤버를 한정할 키워드입니다.  
  
 이벤트 소스 및 수신기가 네이티브 C++ 또는 COM이거나 관리되는지(.NET Framework)에 따라 다음 구문을 이벤트로 사용할 수 있습니다.  
  
|네이티브 C++|COM|관리됨(.NET Framework)|  
|------------------|---------|--------------------------------|  
|메서드|—|메서드|  
|—|interface(인터페이스)|—|  
|—|—|데이터 멤버|  
  
 사용 하 여 [__hook](../cpp/hook.md) 처리기 메서드를 이벤트 메서드와 연결할 이벤트 수신기에서. 사용 하 여 이벤트를 만든 후 합니다 **__event** 키워드 이벤트가 호출 될 때 호출 될 이후에 해당 이벤트에 후크된 모든 이벤트 처리기입니다.  
  
 **__event** 메서드 선언에는 정의 사용할 수 없습니다; 일반 메서드인 것 처럼 이벤트 메서드를 호출할 수 있도록 정의 암시적으로 생성 합니다.  
  
> [!NOTE]
>  템플릿 기반 클래스 또는 구조체에 event를 포함시킬 수 없습니다.  
  
## <a name="native-events"></a>네이티브 이벤트  
 네이티브 이벤트는 메서드입니다. 반환 형식은 일반적으로 HRESULT 또는 **void**, 정수 계열 형식일 수 있지만 포함 하는 **열거형**합니다. 이벤트가 정수 계열 반환 형식을 사용하는 경우 이벤트 처리기가 0이 아닌 값을 반환할 때 오류 조건이 정의됩니다. 이 경우 발생하는 이벤트는 다른 대리자를 호출합니다.  
  
```cpp 
// Examples of native C++ events:  
__event void OnDblClick();  
__event HRESULT OnClick(int* b, char* s);  
```  
  
 참조 [네이티브 c + +에서 이벤트 처리](../cpp/event-handling-in-native-cpp.md) 샘플 코드에 대 한 합니다.  
  
## <a name="com-events"></a>COM 이벤트  
 COM 이벤트는 인터페이스입니다. 이벤트 소스 인터페이스의 메서드 매개 변수 여야 `in` 매개 변수 (그러나 엄격 하 게 적용 되지) 때문에 `out` 매개 변수는 멀티 캐스팅 시 유용 하지 않습니다. 사용 하는 경우는 수준 1 경고가 발행 됩니다는 `out` 매개 변수입니다.  
  
 반환 형식은 일반적으로 HRESULT 또는 **void**에서 정수 계열 형식일 수 있지만 포함 **열거형**합니다. 이벤트가 정수 계열 반환 형식을 사용하고 이벤트 처리기가 0이 아닌 값을 반환하는 경우는 오류 조건이며 이 경우 발생하는 이벤트가 다른 대리자에 대한 호출을 중단합니다. 컴파일러는 자동으로 이벤트 소스 인터페이스를 표시 하는 점에 유의 한 [원본](../windows/source-cpp.md) 생성된 된 IDL에서.  
  
 합니다 [__interface](../cpp/interface.md) 키워드는 후 필요에 따라 항상 **__event** COM 이벤트 원본에 대 한 합니다.  
  
```cpp 
// Example of a COM event:  
__event __interface IEvent1;  
```  
  
 참조 [COM에서 이벤트 처리](../cpp/event-handling-in-com.md) 샘플 코드에 대 한 합니다.  
  
## <a name="managed-events"></a>관리되는 이벤트  
 새 구문의 이벤트 코딩에 대 한 내용은 참조 하세요 [이벤트](../windows/event-cpp-component-extensions.md)합니다.  
  
 관리되는 이벤트는 데이터 멤버 또는 메서드입니다. 이벤트를 사용 하는 경우 대리자의 반환 형식을 준수 해야 합니다 [공용 언어 사양](/dotnet/standard/language-independence-and-language-independent-components)합니다. 이벤트 처리기의 반환 형식은 대리자의 반환 형식과 일치해야 합니다. 대리자에 대 한 자세한 내용은 참조 하세요. [대리자 및 이벤트](../dotnet/delegates-and-events.md)합니다. 관리되는 이벤트가 데이터 멤버인 경우 그 형식은 대리자에 대한 포인터여야 합니다.  
  
 .NET Framework에서 데이터 멤버를 메서드(즉, 해당 대리자의 `Invoke` 메서드) 자체인 것처럼 취급할 수 있습니다. 관리되는 이벤트 데이터 멤버를 선언하기 위한 대리자 형식을 미리 정의해야 합니다. 반면에 관리되는 이벤트 메서드는 해당 관리되는 대리자(이미 정의되지 않은 경우)를 암시적으로 정의합니다. 예를 들어 `OnClick`과 같은 이벤트 값을 다음과 같이 이벤트로 선언할 수 있습니다.  
  
```cpp 
// Examples of managed events:  
__event ClickEventHandler* OnClick;  // data member as event  
__event void OnClick(String* s);  // method as event  
```  
  
 관리되는 이벤트를 암시적으로 선언할 때 이벤트 처리기가 추가되거나 제거되는 경우 호출될 add 및 remove 접근자를 지정할 수 있습니다. 클래스 외부에서 이벤트를 호출하는(발생시키는) 메서드를 정의할 수도 있습니다.  
  
## <a name="example-native-events"></a>예제: 네이티브 이벤트  
  
```cpp 
// EventHandling_Native_Event.cpp  
// compile with: /c  
[event_source(native)]  
class CSource {  
public:  
   __event void MyEvent(int nValue);  
};  
```  
  
## <a name="example-com-events"></a>예제: COM 이벤트  
  
```cpp 
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
  
## <a name="see-also"></a>참고 항목  
 [키워드](../cpp/keywords-cpp.md)   
 [이벤트 처리](../cpp/event-handling.md)   
 [event_source](../windows/event-source.md)   
 [event_receiver](../windows/event-receiver.md)   
 [__hook](../cpp/hook.md)   
 [__unhook](../cpp/unhook.md)   
 [__raise](../cpp/raise.md)