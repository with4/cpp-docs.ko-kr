---
title: "event_source | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.event_source"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "이벤트 처리, 특성"
  - "이벤트 로그, 이벤트 소스"
  - "이벤트 소스, 만들기"
  - "event_source 특성"
  - "이벤트 소스"
  - "이벤트 처리, 이벤트 소스 만들기"
ms.assetid: 0983e36a-6127-4fbb-8a22-8dfec6564c16
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# event_source
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이벤트 소스를 만듭니다.  
  
## 구문  
  
```  
  
       [ event_source(  
       type,  
optimize=[speed | size],  
decorate=[true | false]) ]  
```  
  
#### 매개 변수  
 `type`  
 다음 값 중 하나의 열거형:  
  
-   `native` \- 관리되지 않는 C\/C\+\+ 코드용\(관리되지 않는 클래스에 대한 기본값\).  
  
-   `com` \- COM 코드용.`type`\=`com`인 경우 `coclass`를 사용해야 합니다. 이 값을 사용하려면 다음 헤더 파일을 포함해야 합니다.  
  
    ```  
    #define _ATL_ATTRIBUTES  
    #include <atlbase.h>  
    #include <atlcom.h>  
    ```  
  
 **optimize**  
 `type`이 **native**인 경우, 클래스의 모든 이벤트에 대해 4바이트의 저장소\(minimum\)가 있음을 나타내기 위해 **optimize\=size**를 지정하거나, 4 \* \(이벤트 수\)바이트의 저장소가 있음을 나타내기 위해 **optimize\=speed**를 지정할 수 있습니다.  
  
 **decorate**  
 `type`이 **native**인 경우 병합된\(.mrg\) 파일의 확장 이름에 바깥쪽 클래스 이름을 포함하지 않아야 함을 나타내려면 **decorate\=false**를 지정할 수 있습니다.[\/Fx](../build/reference/fx-merge-injected-code.md)로는 .mrg 파일을 생성할 수 있습니다. 기본값인 **decorate\= false**를 사용하면 병합된 파일에 정규화된 형식 이름이 생성됩니다.  
  
## 설명  
 **event\_source** C\+\+ 특성은, 이 특성이 적용되는 클래스 또는 구조가 이벤트 소스가 될 것임을 지정합니다.  
  
 **event\_source**는 [event\_receiver](../windows/event-receiver.md) 특성 및 [\_\_event](../cpp/event.md) 키워드와 함께 사용됩니다. 이벤트 수신기를 만들려면 **event\_receiver**를 사용합니다. 메서드를 이벤트로 지정하려면 이벤트 소스 내 해당 메서드에 `__event`를 사용합니다.  
  
> [!NOTE]
>  템플릿 기반 클래스 또는 구조체에 event를 포함시킬 수 없습니다.  
  
## 요구 사항  
  
### 특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|**class**, `struct`|  
|**반복 가능**|아니요|  
|**필수 특성**|`type`\=**com**일 때 **coclass**|  
|**잘못된 특성**|없음|  
  
 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## 참고 항목  
 [Compiler Attributes](../windows/compiler-attributes.md)   
 [event\_receiver](../windows/event-receiver.md)   
 [\_\_event](../cpp/event.md)   
 [\_\_hook](../cpp/hook.md)   
 [\_\_unhook](../cpp/unhook.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)