---
title: "SRWLockSharedTraits 구조체 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits
dev_langs:
- C++
helpviewer_keywords:
- SRWLockSharedTraits structure
ms.assetid: 709cb51e-d70c-40b6-bdb4-d8eacf3af495
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cadf94f1d336de7bac13572a045e7ac8487013cf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="srwlocksharedtraits-structure"></a>SRWLockSharedTraits 구조체
공유 잠금 모드의 SRWLock 클래스의 일반적인 특성에 설명합니다.  
  
## <a name="syntax"></a>구문  
  
```  
struct SRWLockSharedTraits;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|`Type`|에 대 한 포인터에 대 한 동의어는 [SRWLOCK](../windows/srwlock-class.md) 클래스입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[SRWLockSharedTraits::GetInvalidValue 메서드](../windows/srwlocksharedtraits-getinvalidvalue-method.md)|항상 유효하지 않은 SRWLockSharedTraits 개체를 가져옵니다.|  
|[SRWLockSharedTraits::Unlock 메서드](../windows/srwlocksharedtraits-unlock-method.md)|지정된 된 SRWLock 개체의 한 독점적인 제어권을 해제합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `SRWLockSharedTraits`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL::Wrappers::HandleTraits 네임스페이스](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)