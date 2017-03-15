---
title: "__unhook | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__unhook"
  - "__unhook_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__unhook 키워드[C++]"
  - "이벤트 처리기, 이벤트 연결 끊기"
ms.assetid: 953a14f3-5199-459d-81e5-fcf015a19878
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# __unhook
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

처리기 메서드를 이벤트에서 분리합니다.  
  
## 구문  
  
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
  
#### 매개 변수  
 **&** *SourceClass* `::` *EventMethod*  
 이벤트 처리기 메서드를 언후크할 이벤트 메서드의 포인터입니다.  
  
-   네이티브 C\+\+ 이벤트: *SourceClass*는 이벤트 소스 클래스이고 *EventMethod*는 이벤트입니다.  
  
-   COM 이벤트: *SourceClass*는 이벤트 소스 인터페이스이고 *EventMethod*는 메서드 중 하나입니다.  
  
-   관리되는 이벤트: *SourceClass*는 이벤트 소스 클래스이고 *EventMethod*는 이벤트입니다.  
  
 `interface`  
 `receiver`에서 언후크되는 인터페이스 이름이며, [event\_receiver](../windows/event-receiver.md) 특성의 *layout\_dependent* 매개 변수가 **true**인 COM 이벤트 수신기 전용입니다.  
  
 *source*  
 이벤트 소스의 인스턴스에 대한 포인터입니다.  **event\_receiver**에 지정된 코드 `type`에 따라 *source*가 다음 중 하나일 수 있습니다.  
  
-   네이티브 이벤트 소스 개체 포인터입니다.  
  
-   **IUnknown** 기반 포인터입니다\(COM 소스\).  
  
-   관리되는 이벤트의 관리되는 개체 포인터입니다.  
  
 **&** *ReceiverClass* `::` `HandlerMethod`  
 이벤트에서 언후크될 이벤트 처리기 메서드의 포인터입니다.  처리기는 클래스의 메서드나 클래스에 대한 참조로 지정됩니다. 클래스 이름을 지정하지 않으면 `__unhook`는 클래스에서 호출된 것으로 가정합니다.  
  
-   네이티브 C\+\+ 이벤트: *ReceiverClass*는 이벤트 수신기 클래스 및 `HandlerMethod` 처리기입니다.  
  
-   COM 이벤트: *ReceiverClass*는 이벤트 수신기 인터페이스이고 `HandlerMethod`는 처리기 중 하나입니다.  
  
-   관리되는 이벤트: *ReceiverClass*는 이벤트 수신기 클래스이고 `HandlerMethod`는 처리기입니다.  
  
 `receiver`\(선택 사항\)  
 이벤트 수신기 클래스의 인스턴스에 대한 포인터입니다.  수신기를 지정하지 않으면 기본값은 `__unhook`가 호출되는 수신기 클래스 또는 구조체입니다.  
  
## 용도  
 이벤트 수신기 클래스 외부의 main을 포함하여 모든 함수 범위에서 사용할 수 있습니다.  
  
## 설명  
 이벤트 메서드에서 처리기 메서드를 분리하거나 "언후크"하기 위해 이벤트 수신기에서 내장 함수 `__unhook`를 사용합니다.  
  
 세 가지 형식의 `__unhook`가 있습니다.  대부분 첫 번째\(인수 4개\) 형식을 사용할 수 있습니다.  COM 이벤트 수신기에만 `__unhook`의 두 번째\(인수 2개\) 형식을 사용할 수 있습니다. 전체 이벤트 인터페이스를 언후크합니다.  세 번째\(인수 1개\) 형식을 사용하여 지정된 소스에서 모든 대리자를 언후크할 수 있습니다.  
  
 0이 아닌 반환 값은 예외가 발생했음을 나타냅니다\(관리되는 이벤트가 예외를 throw함\).  
  
 아직 후크되지 않은 이벤트 및 이벤트 처리기에서 `__unhook`를 호출할 경우 아무 효과도 없습니다.  
  
 컴파일할 때 컴파일러는 이벤트가 있는지 확인하고 지정된 처리기를 사용하여 매개 변수 형식을 검사합니다.  
  
 COM 이벤트 예외와 함께 이벤트 수신기 밖에서 `__hook` 및 `__unhook`를 호출할 수 있습니다.  
  
 `__unhook`를 사용하는 대신 \-\= 연산자를 사용합니다.  
  
 새 구문의 관리되는 이벤트 코딩에 대한 자세한 내용은 [event](../windows/event-cpp-component-extensions.md)를 참조하십시오.  
  
> [!NOTE]
>  템플릿 기반 클래스 또는 구조체에 event를 포함시킬 수 없습니다.  
  
## 예제  
 샘플을 보려면 [네이티브 C\+\+에서 이벤트 처리](../cpp/event-handling-in-native-cpp.md) 및 [COM에서 이벤트 처리](../cpp/event-handling-in-com.md)를 참조하십시오.  
  
## 참고 항목  
 [C\+\+ 키워드](../cpp/keywords-cpp.md)   
 [event\_source](../windows/event-source.md)   
 [event\_receiver](../windows/event-receiver.md)   
 [\_\_event](../cpp/event.md)   
 [\_\_hook](../cpp/hook.md)   
 [\_\_raise](../cpp/raise.md)