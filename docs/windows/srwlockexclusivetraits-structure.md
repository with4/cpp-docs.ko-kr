---
title: SRWLockExclusiveTraits 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits
dev_langs:
- C++
helpviewer_keywords:
- SRWLockExclusiveTraits structure
ms.assetid: 38a996ef-c2d7-4886-b413-a426ecee8f05
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 49f1f50b3fa9e34da8831c1cec138b6aefec27a5
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39649275"
---
# <a name="srwlockexclusivetraits-structure"></a>SRWLockExclusiveTraits 구조체
일반적인 특징을 설명 합니다 `SRWLock` 배타적 잠금 모드의 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```  
struct SRWLockExclusiveTraits;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|`Type`|동의어에 대 한 포인터를 [SRWLOCK](../windows/srwlock-class.md) 클래스입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[SRWLockExclusiveTraits::GetInvalidValue 메서드](../windows/srwlockexclusivetraits-getinvalidvalue-method.md)|검색을 **SRWLockExclusiveTraits** 항상 유효 하지 않은 개체입니다.|  
|[SRWLockExclusiveTraits::Unlock 메서드](../windows/srwlockexclusivetraits-unlock-method.md)|지정 된 한 독점적인 제어권을 해제 `SRWLock` 개체입니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `SRWLockExclusiveTraits`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL::Wrappers::HandleTraits 네임스페이스](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)