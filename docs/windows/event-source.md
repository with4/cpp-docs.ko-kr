---
title: event_source | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.event_source
dev_langs:
- C++
helpviewer_keywords:
- event handling, attributes
- event logs, event source
- event sources, creating
- event_source attribute
- event sources
- event handling, creating event source
ms.assetid: 0983e36a-6127-4fbb-8a22-8dfec6564c16
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 05371b5c2d9acd091adcbdf81d2994f205e36ef7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="eventsource"></a>event_source
이벤트 소스를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      [ event_source(  
   type,  
   optimize=[speed | size],  
   decorate=[true | false]  
) ]  
```  
  
#### <a name="parameters"></a>매개 변수  
 `type`  
 다음 값 중 하나의 열거형:  
  
-   `native` - 관리되지 않는 C/C++ 코드용(관리되지 않는 클래스에 대한 기본값).  
  
-   `com` - COM 코드용. 사용 해야 `coclass` 때 `type` = `com`합니다. 이 값을 사용하려면 다음 헤더 파일을 포함해야 합니다.  
  
    ```  
    #define _ATL_ATTRIBUTES  
    #include <atlbase.h>  
    #include <atlcom.h>  
    ```  
  
 **optimize**  
 `type` 이 **native**인 경우, 클래스의 모든 이벤트에 대해 4바이트의 저장소(minimum)가 있음을 나타내기 위해 **optimize=size**를 지정하거나, 4 * (이벤트 수)바이트의 저장소가 있음을 나타내기 위해 **optimize=speed** 를 지정할 수 있습니다.  
  
 **decorate**  
 `type` 이 **native**인 경우 병합된(.mrg) 파일의 확장 이름에 바깥쪽 클래스 이름을 포함하지 않아야 함을 나타내려면 **decorate=false**를 지정할 수 있습니다. [/Fx](../build/reference/fx-merge-injected-code.md) 로는 .mrg 파일을 생성할 수 있습니다. 기본값인**decorate= false**를 사용하면 병합된 파일에 정규화된 형식 이름이 생성됩니다.  
  
## <a name="remarks"></a>설명  
 **event_source** C++ 특성은, 이 특성이 적용되는 클래스 또는 구조가 이벤트 소스가 될 것임을 지정합니다.  
  
 **event_source** 는 [event_receiver](../windows/event-receiver.md) 특성 및 [__event](../cpp/event.md) 키워드와 함께 사용됩니다. 이벤트 수신기를 만들려면 **event_receiver** 를 사용합니다. 메서드를 이벤트로 지정하려면 이벤트 소스 내 해당 메서드에 `__event` 를 사용합니다.  
  
> [!NOTE]
>  템플릿 기반 클래스 또는 구조체에 event를 포함시킬 수 없습니다.  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|**class**, `struct`|  
|**반복 가능**|아니요|  
|**필수 특성**|**type** = `type`=**com**|  
|**잘못된 특성**|없음|  
  
 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 특성](../windows/compiler-attributes.md)   
 [event_receiver](../windows/event-receiver.md)   
 [__event](../cpp/event.md)   
 [__hook](../cpp/hook.md)   
 [__unhook](../cpp/unhook.md)   
 [클래스 특성](../windows/class-attributes.md)   
