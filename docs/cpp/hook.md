---
title: "__hook | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__hook_cpp"
  - "__hook"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__hook 키워드[C++]"
  - "이벤트 처리기, 이벤트 연결"
ms.assetid: f4cabb10-d293-4c0e-a1d2-4745ef9cc22c
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# __hook
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

처리기 메서드를 이벤트와 연결합니다.  
  
## 구문  
  
```  
  
      long __hook(  
   &SourceClass::EventMethod,  
   source,  
   &ReceiverClass::HandlerMethod  
   [, receiver = this]  
);  
long __hook(  
   interface,  
   source  
);  
```  
  
#### 매개 변수  
 **&** *SourceClass* `::` *EventMethod*  
 이벤트 처리기 메서드를 후크할 이벤트 메서드에 대한 포인터입니다.  
  
-   네이티브 C\+\+ 이벤트: *SourceClass*는 이벤트 소스 클래스이고 *EventMethod*는 이벤트입니다.  
  
-   COM 이벤트: *SourceClass*는 이벤트 소스 인터페이스이고 *EventMethod*는 메서드 중 하나입니다.  
  
-   관리되는 이벤트: *SourceClass*는 이벤트 소스 클래스이고 *EventMethod*는 이벤트입니다.  
  
 `interface`  
 `receiver`에 후크되는 인터페이스의 이름입니다. [event\_receiver](../windows/event-receiver.md) 특성의 *layout\_dependent* 매개 변수가 **true**인 COM 이벤트 수신기에만 해당합니다.  
  
 *source*  
 이벤트 소스의 인스턴스에 대한 포인터입니다.  **event\_receiver**에 지정된 코드 `type`에 따라 *source*가 다음 중 하나일 수 있습니다.  
  
-   네이티브 이벤트 소스 개체 포인터입니다.  
  
-   **IUnknown** 기반 포인터입니다\(COM 소스\).  
  
-   관리되는 이벤트의 관리되는 개체 포인터입니다.  
  
 **&** *ReceiverClass* `::` `HandlerMethod`  
 이벤트에 후크될 이벤트 처리기 메서드에 대한 포인터입니다.  처리기는 클래스의 메서드나 이에 대한 참조로 지정됩니다. 클래스 이름을 지정하지 않은 경우 `__hook`는 자신이 호출된 클래스를 해당 클래스로 가정합니다.  
  
-   네이티브 C\+\+ 이벤트: *ReceiverClass*는 이벤트 수신기 클래스 및 `HandlerMethod` 처리기입니다.  
  
-   COM 이벤트: *ReceiverClass*는 이벤트 수신기 인터페이스이고 `HandlerMethod`는 처리기 중 하나입니다.  
  
-   관리되는 이벤트: *ReceiverClass*는 이벤트 수신기 클래스이고 `HandlerMethod`는 처리기입니다.  
  
 `receiver`\(선택 사항\)  
 이벤트 수신기 클래스의 인스턴스에 대한 포인터입니다.  수신기를 지정하지 않는 경우 기본값은 `__hook`가 호출되는 수신기 클래스 또는 구조체입니다.  
  
## 용도  
 이벤트 수신기 클래스 외부의 main을 포함하여 모든 함수 범위에서 사용할 수 있습니다.  
  
## 설명  
 이벤트 수신기에서 `__hook` 내장 함수를 사용하여 처리기 메서드를 이벤트 메서드와 연결하거나 후크할 수 있습니다.  이렇게 하면 소스에서 지정된 이벤트를 발생시킬 때 지정된 처리기가 호출됩니다.  여러 처리기를 단일 이벤트에 후크하거나 여러 이벤트를 단일 처리기에 후크할 수 있습니다.  
  
 두 가지 형태의 `__hook`가 있습니다.  대부분의 경우에 첫 번째 형태\(인수 4개\)를 사용할 수 있으며, 특히 [event\_receiver](../windows/event-receiver.md) 특성의 *layout\_dependent* 매개 변수가 **false**인 COM 이벤트 수신기에 사용할 수 있습니다.  
  
 이러한 경우 메서드 중 하나에서 이벤트를 발생시키기 전에 인터페이스에서 모든 메서드를 후크할 필요는 없습니다. 이벤트를 처리하는 메서드만 후크해야 합니다.  *layout\_dependent***\=true**인 COM 이벤트 수신기에만 두 번째 형태\(인수 2개\)의 `__hook`를 사용할 수 있습니다.  
  
 `__hook`는 long 값을 반환합니다.  0이 아닌 반환 값은 오류가 발생했음을 나타냅니다\(관리되는 이벤트가 예외를 throw함\).  
  
 컴파일러는 이벤트가 있는지 확인하고 이벤트 시그니처가 대리자 시그니처와 일치하는지 확인합니다.  
  
 COM 이벤트 예외와 함께 이벤트 수신기 밖에서 `__hook` 및 `__unhook`를 호출할 수 있습니다.  
  
 `__hook`를 사용하는 대신 \+\= 연산자를 사용할 수 있습니다.  
  
 새 구문의 관리되는 이벤트 코딩에 대한 자세한 내용은 [event](../windows/event-cpp-component-extensions.md)를 참조하십시오.  
  
> [!NOTE]
>  템플릿 기반 클래스 또는 구조체에 event를 포함시킬 수 없습니다.  
  
## 예제  
 샘플을 보려면 [네이티브 C\+\+에서 이벤트 처리](../cpp/event-handling-in-native-cpp.md) 및 [COM에서 이벤트 처리](../cpp/event-handling-in-com.md)를 참조하십시오.  
  
## 참고 항목  
 [C\+\+ 키워드](../cpp/keywords-cpp.md)   
 [이벤트 처리](../cpp/event-handling.md)   
 [event\_source](../windows/event-source.md)   
 [event\_receiver](../windows/event-receiver.md)   
 [\_\_unhook](../cpp/unhook.md)   
 [\_\_raise](../cpp/raise.md)