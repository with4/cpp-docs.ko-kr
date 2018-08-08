---
title: EventSource 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 03/22/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::EventSource
dev_langs:
- C++
helpviewer_keywords:
- EventSource class
ms.assetid: 91f1c072-6af4-44e6-b6d8-ac6d0c688dde
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a98d8997ebfb5b21b3e469b2aacca15cde4a5319
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39570537"
---
# <a name="eventsource-class"></a>EventSource 클래스
Agile이 아닌 이벤트를 나타냅니다. **EventSource** 멤버 함수 추가, 제거 및 이벤트 처리기를 호출 합니다. Agile 이벤트를 사용 하 여 [AgileEventSource](agileeventsource-class.md)합니다. 
  
## <a name="syntax"></a>구문  
  
```  
template<typename TDelegateInterface>  
class EventSource;  
```  
  
### <a name="parameters"></a>매개 변수  
 *TDelegateInterface*  
 인터페이스 이벤트 처리기를 나타내는 대리자입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[EventSource::EventSource 생성자](../windows/eventsource-eventsource-constructor.md)|새 인스턴스를 초기화 합니다 **EventSource** 클래스입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[EventSource::Add 메서드](../windows/eventsource-add-method.md)|현재 이벤트 처리기 집합에 지정 된 대리자를 인터페이스에 의해 표시 되는 이벤트 처리기 추가 **EventSource** 개체입니다.|  
|[EventSource::GetSize 메서드](../windows/eventsource-getsize-method.md)|현재 연결 된 이벤트 처리기의 수를 검색 **EventSource** 개체|  
|[EventSource::InvokeAll 메서드](../windows/eventsource-invokeall-method.md)|현재 연결 된 각 이벤트 처리기를 호출 **EventSource** 지정 된 인수 형식 및 인수를 사용 하 여 개체입니다.|  
|[EventSource::Remove 메서드](../windows/eventsource-remove-method.md)|현재 연결 된 이벤트 처리기 집합에서 지정 된 이벤트 등록 토큰을 나타내는 이벤트 처리기를 삭제 **EventSource** 개체입니다.|  
  
### <a name="protected-data-members"></a>보호된 데이터 멤버  
  
|name|설명|  
|----------|-----------------|  
|[EventSource::addRemoveLock_ 데이터 멤버](../windows/eventsource-addremovelock-data-member.md)|에 대 한 액세스를 동기화 합니다 [targets_](../windows/eventsource-targets-data-member.md) 배열을 추가 하는 경우, 제거 또는 이벤트 처리기를 호출 합니다.|  
|[EventSource::targets_ 데이터 멤버](../windows/eventsource-targets-data-member.md)|하나 이상의 이벤트 처리기 배열입니다.|  
|[EventSource::targetsPointerLock_ 데이터 멤버](../windows/eventsource-targetspointerlock-data-member.md)|이 EventSource의 이벤트 처리기를 추가, 삭제 또는 호출하는 동안에도 내부 데이터 멤버에 대한 액세스를 동기화합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `EventSource`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** event.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)  
 [AgileEventSource 클래스](agileeventsource-class.md)