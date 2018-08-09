---
title: event_receiver | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.event_receiver
dev_langs:
- C++
helpviewer_keywords:
- event_receiver attribute
- event receivers
- events [C++], event receivers (sinks)
- event handling [C++], attributes
- event handling [C++], creating receiver
- event sinks, creating
- event sinks
ms.assetid: bf8fe770-3ea2-4128-b46b-166222ee4097
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2b1b285437170c4059d5cd0d66d19188c99badd9
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39646788"
---
# <a name="eventreceiver"></a>event_receiver
이벤트 수신기(싱크)를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
[ event_receiver(  
   type   
   [, layout_dependent=false]   
) ]  
```  
  
### <a name="parameters"></a>매개 변수  
 *type*  
 다음 값 중 하나의 열거형:  
  
-   `native` 관리 되지 않는 C/c + + 코드 (기본 클래스에 대 한 기본값).  
  
-   `com` - COM 코드용. 이 값을 사용하려면 다음 헤더 파일을 포함해야 합니다.  
  
    ```cpp  
    #define _ATL_ATTRIBUTES  
    #include <atlbase.h>  
    #include <atlcom.h>  
    ```  
  
 *layout_dependent*  
 지정할 *layout_dependent* 경우에만 `type` = **com**합니다. *layout_dependent* 는 부울입니다.  
  
-   **true** 수신기 일치 해야 하는 후크 되어 이벤트 소스 이벤트에서 대리자의 시그니처와 의미 합니다. 이벤트 수신기 처리기 이름은 관련 이벤트 소스 인터페이스에 지정 된 이름과 일치 해야 합니다. 사용 해야 합니다 `coclass` 때 *layout_dependent* 됩니다 **true**합니다. 것이 약간 더 효율적 지정할 **true**합니다.  
  
-   **false** (기본값) 즉, 호출 규칙 및 저장소 클래스 (가상, 정적, 등)를 이벤트 메서드와 처리기;와 일치 하지 않아도 또는 처리기 이름은 필요가 이벤트 소스 인터페이스 메서드 이름과 일치 합니다.  
  
## <a name="remarks"></a>설명  
 합니다 **event_receiver** c + + 특성 클래스 또는 구조체 적용 되는 Visual c + + 통합된 이벤트 모델을 사용 하 여 이벤트 수신기, 될 것임을 지정 합니다.  
  
 **event_receiver** 사용 되는 [event_source](../windows/event-source.md) 특성 및 [__hook](../cpp/hook.md) 하 고 [__unhook](../cpp/unhook.md) 키워드. 사용 하 여 `event_source` 이벤트 원본을 만들 수 있습니다. 사용 하 여 **__hook** 이벤트 원본의 이벤트에 이벤트 수신기 메서드 ("후크")에 연결할 이벤트 수신기의 메서드 내에서. 사용 하 여 **__unhook** 을 분리 합니다.  
  
 *layout_dependent* COM 이벤트 수신기만 지정 됩니다 (`type`=**com**). 에 대 한 기본 *layout_dependent* 됩니다 **false**합니다.  
  
> [!NOTE]
>  템플릿 기반 클래스 또는 구조체에 event를 포함시킬 수 없습니다.  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|**클래스**, **구조체**|  
|**반복 가능**|아니요|  
|**필수 특성**|`coclass` 때 *layout_dependent*=**true**|  
|**잘못된 특성**|없음|  
  
 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 특성](../windows/compiler-attributes.md)   
 [event_source](../windows/event-source.md)   
 [__event](../cpp/event.md)   
 [__hook](../cpp/hook.md)   
 [__unhook](../cpp/unhook.md)   
 [클래스 특성](../windows/class-attributes.md)   