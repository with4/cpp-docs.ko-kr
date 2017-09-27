---
title: __unhook | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __unhook
- __unhook_cpp
dev_langs:
- C++
helpviewer_keywords:
- event handlers, dissociating events
- __unhook keyword [C++]
ms.assetid: 953a14f3-5199-459d-81e5-fcf015a19878
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 2b1909cf5d7bde440d434bb44ff2276e68679e78
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="unhook"></a>__unhook
처리기 메서드를 이벤트에서 분리합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      long  __unhook(  
   &SourceClass::EventMethod,  
   source,  
   &ReceiverClass::HandlerMethod  
   [, receiver = this]   
);  
long  __unhook(   
   interface,  
   source  
);  
long  __unhook(  
   source   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 **&***SourceClass* `::` *EventMethod*  
 이벤트 처리기 메서드를 언후크할 이벤트 메서드의 포인터입니다.  
  
-   네이티브 c + + 이벤트: *SourceClass* 는 이벤트 소스 클래스 및 *EventMethod* 이벤트입니다.  
  
-   COM 이벤트: *SourceClass* 는 이벤트 소스 인터페이스 및 *EventMethod* 메서드 중 하나입니다.  
  
-   관리 되는 이벤트: *SourceClass* 는 이벤트 소스 클래스 및 *EventMethod* 이벤트입니다.  
  
 `interface`  
 후크 되는 인터페이스 이름이 `receiver`, COM 이벤트 수신기에 대해서만 *layout_dependent* 의 매개 변수는 [event_receiver](../windows/event-receiver.md) 특성은 **true**.  
  
 *소스*  
 이벤트 소스의 인스턴스에 대한 포인터입니다. 코드에 따라 `type` 에 지정 된 **event_receiver**, *소스* 다음 중 하나일 수 있습니다.  
  
-   네이티브 이벤트 소스 개체 포인터입니다.  
  
-   **IUnknown**-기반 포인터 (COM 소스).  
  
-   관리되는 이벤트의 관리되는 개체 포인터입니다.  
  
 **&***ReceiverClass* `::``HandlerMethod`  
 이벤트에서 언후크될 이벤트 처리기 메서드의 포인터입니다. 처리기는 클래스의 메서드나 클래스에 대한 참조로 지정됩니다. 클래스 이름을 지정하지 않으면 `__unhook`는 클래스에서 호출된 것으로 가정합니다.  
  
-   네이티브 c + + 이벤트: *ReceiverClass* 는 이벤트 수신기 클래스 및 `HandlerMethod` 처리기입니다.  
  
-   COM 이벤트: *ReceiverClass* 는 이벤트 수신기 인터페이스 및 `HandlerMethod` 처리기 중 하나입니다.  
  
-   관리 되는 이벤트: *ReceiverClass* 는 이벤트 수신기 클래스 및 `HandlerMethod` 처리기입니다.  
  
 `receiver`(선택 사항)  
 이벤트 수신기 클래스의 인스턴스에 대한 포인터입니다. 수신기를 지정하지 않으면 기본값은 `__unhook`가 호출되는 수신기 클래스 또는 구조체입니다.  
  
## <a name="usage"></a>용도  
 이벤트 수신기 클래스 외부의 main을 포함하여 모든 함수 범위에서 사용할 수 있습니다.  
  
## <a name="remarks"></a>설명  
 이벤트 메서드에서 처리기 메서드를 분리하거나 "언후크"하기 위해 이벤트 수신기에서 내장 함수 `__unhook`를 사용합니다.  
  
 세 가지 형식의 `__unhook`가 있습니다. 대부분 첫 번째(인수 4개) 형식을 사용할 수 있습니다. COM 이벤트 수신기에만 `__unhook`의 두 번째(인수 2개) 형식을 사용할 수 있습니다. 전체 이벤트 인터페이스를 언후크합니다. 세 번째(인수 1개) 형식을 사용하여 지정된 소스에서 모든 대리자를 언후크할 수 있습니다.  
  
 0이 아닌 반환 값은 예외가 발생했음을 나타냅니다(관리되는 이벤트가 예외를 throw함).  
  
 아직 후크되지 않은 이벤트 및 이벤트 처리기에서 `__unhook`를 호출할 경우 아무 효과도 없습니다.  
  
 컴파일할 때 컴파일러는 이벤트가 있는지 확인하고 지정된 처리기를 사용하여 매개 변수 형식을 검사합니다.  
  
 COM 이벤트 예외와 함께 이벤트 수신기 밖에서 `__hook` 및 `__unhook`를 호출할 수 있습니다.  
  
 `__unhook`를 사용하는 대신 -= 연산자를 사용합니다.  
  
 에 대 한 내용은 새 구문에서 관리 되는 이벤트를 코딩 하십시오 [이벤트](../windows/event-cpp-component-extensions.md)합니다.  
  
> [!NOTE]
>  템플릿 기반 클래스 또는 구조체에 event를 포함시킬 수 없습니다.  
  
## <a name="example"></a>예제  
 참조 [네이티브 c + +에서 이벤트 처리](../cpp/event-handling-in-native-cpp.md) 및 [COM에서 이벤트 처리](../cpp/event-handling-in-com.md) 샘플에 대 한 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [키워드](../cpp/keywords-cpp.md)   
 [event_source](../windows/event-source.md)   
 [event_receiver](../windows/event-receiver.md)   
 [__event](../cpp/event.md)   
 [__hook](../cpp/hook.md)   
 [__raise](../cpp/raise.md)
