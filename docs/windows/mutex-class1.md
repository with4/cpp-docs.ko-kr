---
title: Mutex 클래스 1 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Mutex
dev_langs:
- C++
helpviewer_keywords:
- Mutex class
ms.assetid: 682a0963-721c-46a2-8871-000e9997505b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cd9c3dbbcbffff32f7c1611b6b49ee19ada7e52c
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39606776"
---
# <a name="mutex-class1"></a>Mutex 클래스 1
공유 리소스를 단독으로 제어하는 동기화 개체를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
class Mutex : public HandleT<HandleTraits::MutexTraits>  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|`SyncLock`|동기 잠금을 지 원하는 클래스에 대 한 동의어입니다.|  
  
### <a name="public-constructor"></a>Public 생성자  
  
|name|설명|  
|----------|-----------------|  
|[Mutex::Mutex 생성자](../windows/mutex-mutex-constructor.md)|새 인스턴스를 초기화 합니다 **뮤텍스** 클래스입니다.|  
  
### <a name="public-members"></a>공용 멤버  
  
|name|설명|  
|----------|-----------------|  
|[Mutex::Lock 메서드](../windows/mutex-lock-method.md)|현재 개체를 때까지 대기 또는 **뮤텍스** 지정된 된 핸들, 뮤텍스 또는 지정 된 시간 제한 간격이 경과 하는 릴리스를 사용 하 여 연결 된 개체입니다.|  
  
### <a name="public-operator"></a>Public 연산자  
  
|name|설명|  
|----------|-----------------|  
|[Mutex::operator= 연산자](../windows/mutex-operator-assign-operator.md)|할당 된 (이동) **뮤텍스** 개체를 현재 **뮤텍스** 개체입니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `Mutex`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL::Wrappers 네임스페이스](../windows/microsoft-wrl-wrappers-namespace.md)