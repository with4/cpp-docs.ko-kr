---
title: 이벤트 클래스 (Windows Runtime c + + 템플릿 라이브러리) | Microsoft Docs
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
ms.openlocfilehash: c07d58f244bf2e7e6c9329196bae7b5bb323ce12
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39644166"
---
# <a name="event-class-windows-runtime-c-template-library"></a>Event 클래스(Windows Runtime C++ 템플릿 라이브러리)
이벤트를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
class Event : public HandleT<HandleTraits::EventTraits>;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[Event::Event 생성자(Windows Runtime C++ 템플릿 라이브러리)](../windows/event-event-constructor-windows-runtime-cpp-template-library.md)|새 인스턴스를 초기화 합니다 **이벤트** 클래스입니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[Event::operator= 연산자](../windows/event-operator-assign-operator.md)|지정 된 할당 **이벤트** 현재 참조 **이벤트** 인스턴스.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `HandleT`  
  
 `Event`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL::Wrappers 네임스페이스](../windows/microsoft-wrl-wrappers-namespace.md)