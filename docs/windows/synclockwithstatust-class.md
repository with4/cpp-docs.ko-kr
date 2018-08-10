---
title: SyncLockWithStatusT 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT
dev_langs:
- C++
helpviewer_keywords:
- SyncLockWithStatusT class
ms.assetid: 4832fd93-0ac8-4168-9404-b43fefea7476
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bd514b1684571fb12a19265b57e6d5b92b8c7edd
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40011551"
---
# <a name="synclockwithstatust-class"></a>SyncLockWithStatusT 클래스
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
template <  
   typename SyncTraits  
>  
class SyncLockWithStatusT : public SyncLockT<SyncTraits>;  
```  
  
### <a name="parameters"></a>매개 변수  
 *SyncTraits*  
 단독으로 사용할 수 있는 형식 또는 리소스의 소유권을 공유 합니다.  
  
## <a name="remarks"></a>설명  
 단독으로 사용할 수 있는 형식을 나타내는 또는 리소스의 소유권을 공유 합니다.  
  
 합니다 **SyncLockWithStatusT** 클래스 구현에 사용 되는 [뮤텍스](../windows/mutex-class1.md) 및 [세마포](../windows/semaphore-class.md) 클래스입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[SyncLockWithStatusT::SyncLockWithStatusT 생성자](../windows/synclockwithstatust-synclockwithstatust-constructor.md)|새 인스턴스를 초기화 합니다 **SyncLockWithStatusT** 클래스입니다.|  
  
### <a name="protected-constructors"></a>Protected 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[SyncLockWithStatusT::SyncLockWithStatusT 생성자](../windows/synclockwithstatust-synclockwithstatust-constructor.md)|새 인스턴스를 초기화 합니다 **SyncLockWithStatusT** 클래스입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[SyncLockWithStatusT::GetStatus 메서드](../windows/synclockwithstatust-getstatus-method.md)|현재 대기 상태를 검색 **SyncLockWithStatusT** 개체입니다.|  
|[SyncLockWithStatusT::IsLocked 메서드](../windows/synclockwithstatust-islocked-method.md)|나타냅니다 여부 현재 **SyncLockWithStatusT** 리소스를 소유 하는 개체입니다. 즉, **SyncLockWithStatusT** 개체가 *잠겨*합니다.|  
  
### <a name="protected-data-members"></a>보호된 데이터 멤버  
  
|name|설명|  
|----------|-----------------|  
|[SyncLockWithStatusT::status_ 데이터 멤버](../windows/synclockwithstatust-status-data-member.md)|현재를 기준으로 개체에 대 한 잠금 작업이 후 기본 대기 작업의 결과 보유 **SyncLockWithStatusT** 개체입니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `SyncLockT`  
  
 `SyncLockWithStatusT`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL::Wrappers::Details 네임스페이스](../windows/microsoft-wrl-wrappers-details-namespace.md)