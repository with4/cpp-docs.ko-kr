---
title: "EventSource 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::EventSource
dev_langs:
- C++
helpviewer_keywords:
- EventSource class
ms.assetid: 91f1c072-6af4-44e6-b6d8-ac6d0c688dde
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 705260547d5a42b463d61b79c38592874f9dfa19
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="eventsource-class"></a>EventSource 클래스
이벤트를 나타냅니다. EventSource 멤버 함수는 추가, 제거 및 이벤트 처리기를 호출 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<  
   typename TDelegateInterface  
>  
class EventSource;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `TDelegateInterface`  
 인터페이스는 이벤트 처리기를 나타내는 대리자입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[EventSource::EventSource 생성자](../windows/eventsource-eventsource-constructor.md)|EventSource 클래스의 새 인스턴스를 초기화합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[EventSource::Add 메서드](../windows/eventsource-add-method.md)|현재 EventSource 개체에 대 한 이벤트 처리기의 집합에 지정 된 대리자 인터페이스를 나타내는 이벤트 처리기를 추가 합니다.|  
|[EventSource::GetSize 메서드](../windows/eventsource-getsize-method.md)|현재 EventSource 개체에 연결된 이벤트 처리기 수를 가져옵니다.|  
|[EventSource::InvokeAll 메서드](../windows/eventsource-invokeall-method.md)|지정된 인수 유형 및 인수를 사용하여 현재 EventSource 개체에 연결된 이벤트 처리기를 호출합니다.|  
|[EventSource::Remove 메서드](../windows/eventsource-remove-method.md)|현재 EventSource 개체에 연결 된 이벤트 처리기의 집합에서 지정 된 이벤트 등록 토큰이 나타내는 이벤트 처리기를 삭제 합니다.|  
  
### <a name="protected-data-members"></a>보호된 데이터 멤버  
  
|name|설명|  
|----------|-----------------|  
|[EventSource::addRemoveLock_ 데이터 멤버](../windows/eventsource-addremovelock-data-member.md)|에 대 한 액세스를 동기화는 [targets_](../windows/eventsource-targets-data-member.md) 배열을 추가 하는 경우, 제거 또는 이벤트 처리기를 호출 합니다.|  
|[EventSource::targets_ 데이터 멤버](../windows/eventsource-targets-data-member.md)|하나 이상의 이벤트 처리기 배열입니다.|  
|[EventSource::targetsPointerLock_ 데이터 멤버](../windows/eventsource-targetspointerlock-data-member.md)|이 EventSource의 이벤트 처리기를 추가, 삭제 또는 호출하는 동안에도 내부 데이터 멤버에 대한 액세스를 동기화합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `EventSource`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** event.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)