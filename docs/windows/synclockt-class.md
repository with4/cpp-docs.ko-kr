---
title: SyncLockT 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT
dev_langs:
- C++
helpviewer_keywords:
- SyncLockT class
ms.assetid: a967f6f7-3555-43d1-b210-2bb65d63d15e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e05a1be5d84db52573d3c3235936ecf82dde5894
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="synclockt-class"></a>SyncLockT 클래스
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <  
   typename SyncTraits  
>  
class SyncLockT;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `SyncTraits`  
 리소스의 소유권을 사용할 수 있는 형식입니다.  
  
## <a name="remarks"></a>설명  
 단독으로 사용할 수 있는 형식을 나타내는 또는 리소스의 소유권을 공유 합니다.  
  
 SyncLockT 클래스는 사용, 예를 들어 구현할 수 있도록는 [SRWLock](../windows/srwlock-class.md) 클래스입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[SyncLockT::SyncLockT 구조체](../windows/synclockt-synclockt-constructor.md)|SyncLockT 클래스의 새 인스턴스를 초기화합니다.|  
|[SyncLockT::~SyncLockT 소멸자](../windows/synclockt-tilde-synclockt-destructor.md)|SyncLockT 클래스의 인스턴스 초기화를 취소 합니다.|  
  
### <a name="protected-constructors"></a>Protected 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[SyncLockT::SyncLockT 구조체](../windows/synclockt-synclockt-constructor.md)|SyncLockT 클래스의 새 인스턴스를 초기화합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[SyncLockT::IsLocked 메서드](../windows/synclockt-islocked-method.md)|현재 SyncLockT 개체는 리소스를 소유 하는지 여부를 나타냅니다. SyncLockT 개체 즉, *잠긴*합니다.|  
|[SyncLockT::Unlock 메서드](../windows/synclockt-unlock-method.md)|있는 경우 현재 SyncLockT 개체에서 보유 하는 리소스의 제어를 해제 합니다.|  
  
### <a name="protected-data-members"></a>보호된 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[SyncLockT::sync_ 데이터 멤버](../windows/synclockt-sync-data-member.md)|SyncLockT 클래스에 의해 표시 되는 기본 리소스를 보유 합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `SyncLockT`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL::Wrappers::Details Namespace](../windows/microsoft-wrl-wrappers-details-namespace.md)   
 [SRWLock 클래스](../windows/srwlock-class.md)