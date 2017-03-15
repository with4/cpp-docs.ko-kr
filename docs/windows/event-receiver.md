---
title: "event_receiver | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.event_receiver"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "event_receiver attribute"
  - "event receivers"
  - "events [C++], event receivers (sinks)"
  - "event handling [C++], attributes"
  - "event handling [C++], creating receiver"
  - "event sinks, creating"
  - "event sinks"
ms.assetid: bf8fe770-3ea2-4128-b46b-166222ee4097
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# event_receiver
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이벤트 수신자 \(싱크\)을 만듭니다.  
  
## 구문  
  
```  
  
      [ event_receiver(  
   type   
   [, layout_dependent=false]   
) ]  
```  
  
#### 매개 변수  
 `type`  
 열거형은 다음 값 중 하나입니다.  
  
-   `native`관리 되지 않는 C\/C\+\+ 코드를 \(기본 클래스 기본값\).  
  
-   `com`COM 코드입니다.  다음 헤더 파일을 포함 하는이 값이 필요 합니다.  
  
    ```  
    #define _ATL_ATTRIBUTES  
    #include <atlbase.h>  
    #include <atlcom.h>  
    ```  
  
 **layout\_dependent**  
 지정한  *layout\_dependent* 경우에만 `type`\=**com**.  *layout\_dependent* 는 부울 값입니다.  
  
-   **true 이면** 대리자 시그니처 즉, 이벤트 수신기를가 연결 이벤트 원본 형식과 일치 해야 합니다.  이벤트 수신기 처리기 이름은 관련 된 이벤트 소스 인터페이스의 지정 된 이름과 일치 해야 합니다.  사용 하 여  **coclass** 때  *layout\_dependent* 입니다  **true**.  지정 하는 것이 보다 효율적입니다  **true**.  
  
-   **false 이면** \(기본값\)을 의미 하는 호출 규칙 및 저장소 클래스 \(가상, 정적, 및 다른 사람\) 이벤트 메서드 처리기; 일치 하지 않아도 없으며 처리기 이름은 이벤트 소스 인터페이스 메서드 이름이 일치 해야 합니다.  
  
## 설명  
 해당  **event\_receiver** C\+\+ 특성 지정 클래스 또는 구조가 적용 되는 Visual C\+\+ 통합된 이벤트 모델을 사용 하 여 이벤트 수신기를 수 있습니다.  
  
 **event\_receiver** 와 함께 사용 되는  [event\_source](../windows/event-source.md) 특성 및  [\_\_hook](../cpp/hook.md) 및  [\_\_unhook](../cpp/unhook.md) 키워드.  사용  **event\_source** 이벤트 소스를 만들 수 있습니다.  사용 `__hook` \("후크"\) 이벤트 수신기 메서드 이벤트를 이벤트 소스에 연결 하려면 이벤트 수신기의 메서드 안에 있는.  사용 `__unhook` 를 연결 합니다.  
  
 *layout\_dependent* 에 대 한 COM 이벤트 수신기만 지정 됩니다 \(`type`\=**com**\).  기본  *layout\_dependent* 입니다  **false**.  
  
> [!NOTE]
>  템플릿 기반 클래스 또는 구조체에 event를 포함시킬 수 없습니다.  
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|**클래스**,`struct`|  
|**반복 가능**|아니요|  
|**필수 특성**|**coclass** 때  *layout\_dependent*\=**true**|  
|**잘못 된 특성**|없음|  
  
 자세한 내용은  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 참고 항목  
 [Compiler Attributes](../windows/compiler-attributes.md)   
 [event\_source](../windows/event-source.md)   
 [\_\_event](../cpp/event.md)   
 [\_\_hook](../cpp/hook.md)   
 [\_\_unhook](../cpp/unhook.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)