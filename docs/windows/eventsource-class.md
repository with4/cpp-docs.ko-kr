---
title: "EventSource 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "event/Microsoft::WRL::EventSource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "EventSource 클래스"
ms.assetid: 91f1c072-6af4-44e6-b6d8-ac6d0c688dde
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# EventSource 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이벤트를 나타냅니다.  EventSource 멤버 함수를 추가, 제거 및 이벤트 처리기를 호출 합니다.  
  
## 구문  
  
```  
template<  
   typename TDelegateInterface  
>  
class EventSource;  
```  
  
#### 매개 변수  
 `TDelegateInterface`  
 인터페이스는 이벤트 처리기를 나타내는 대리자입니다.  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[EventSource::EventSource 생성자](../windows/eventsource-eventsource-constructor.md)|EventSource 클래스의 새 인스턴스를 초기화합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[EventSource::Add 메서드](../windows/eventsource-add-method.md)|현재 이벤트 소스 개체를 위한 이벤트 처리기의 집합에 대한 지정된 대리자 인터페이스에 의해 표현된 이벤트 처리기를 첨부합니다.|  
|[EventSource::GetSize 메서드](../windows/eventsource-getsize-method.md)|현재 EventSource 개체와 연결된 이벤트 처리기의 수를 검색 합니다.|  
|[EventSource::InvokeAll 메서드](../windows/eventsource-invokeall-method.md)|지정된 인수 형식 및 인수를 사용하여 현재 EventSource 개체와 연결 된 각 이벤트 처리기가 호출 됩니다.|  
|[EventSource::Remove 메서드](../windows/eventsource-remove-method.md)|현재 EventSource 개체와 연결 된 이벤트 처리기 집합에서 등록 지정 된 이벤트 토큰이 나타내는 이벤트 처리기를 삭제 합니다.|  
  
### 보호된 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[EventSource::addRemoveLock\_ 데이터 멤버](../windows/eventsource-addremovelock-data-member.md)|동기화에 대한 액세스는 [targets\_](../windows/eventsource-targets-data-member.md) 배열을 추가, 제거 하거나 이벤트 처리기를 호출 합니다.|  
|[EventSource::targets\_ 데이터 멤버](../windows/eventsource-targets-data-member.md)|하나 이상의 이벤트 처리기의 배열입니다.|  
|[EventSource::targetsPointerLock\_ 데이터 멤버](../windows/eventsource-targetspointerlock-data-member.md)|이 EventSource에 대한 이벤트 처리기를 추가 하는 동안, 제거하거나 호출 내부 데이터 멤버에 대한 액세스를 동기화 합니다.|  
  
## 상속 계층  
 `EventSource`  
  
## 요구 사항  
 **헤더:** event.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)