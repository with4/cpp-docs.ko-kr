---
title: SRWLockSharedTraits 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits
dev_langs:
- C++
helpviewer_keywords:
- SRWLockSharedTraits structure
ms.assetid: 709cb51e-d70c-40b6-bdb4-d8eacf3af495
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c606a1a7d32a02442e767a31543a76a4dccf295e
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39652476"
---
# <a name="srwlocksharedtraits-structure"></a>SRWLockSharedTraits 구조체
일반적인 특징을 설명 합니다 `SRWLock` 공유 잠금 모드의 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```  
struct SRWLockSharedTraits;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|`Type`|동의어에 대 한 포인터를 [SRWLOCK](../windows/srwlock-class.md) 클래스입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[SRWLockSharedTraits::GetInvalidValue 메서드](../windows/srwlocksharedtraits-getinvalidvalue-method.md)|검색을 **SRWLockSharedTraits** 항상 유효 하지 않은 개체입니다.|  
|[SRWLockSharedTraits::Unlock 메서드](../windows/srwlocksharedtraits-unlock-method.md)|지정 된 한 독점적인 제어권을 해제 `SRWLock` 개체입니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `SRWLockSharedTraits`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL::Wrappers::HandleTraits 네임스페이스](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)