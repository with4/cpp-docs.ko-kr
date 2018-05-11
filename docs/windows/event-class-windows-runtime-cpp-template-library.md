---
title: 이벤트 클래스 (Windows 런타임 c + + 템플릿 라이브러리) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Event
dev_langs:
- C++
ms.assetid: 55dfc9fc-62d4-4bb2-9d85-5b6dd88569e8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 12c9e5bfe01de0a9864ff1e94364e0c42178ad11
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="event-class-windows-runtime-c-template-library"></a>Event 클래스(Windows Runtime C++ 템플릿 라이브러리)
이벤트를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
class Event : public HandleT<HandleTraits::EventTraits>;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[Event::Event 생성자(Windows Runtime C++ 템플릿 라이브러리)](../windows/event-event-constructor-windows-runtime-cpp-template-library.md)|이벤트 클래스의 새 인스턴스를 초기화합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[Event::operator= 연산자](../windows/event-operator-assign-operator.md)|현재 이벤트 인스턴스를 지정된 이벤트 참조를 할당합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `HandleT`  
  
 `Event`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL::Wrappers 네임스페이스](../windows/microsoft-wrl-wrappers-namespace.md)