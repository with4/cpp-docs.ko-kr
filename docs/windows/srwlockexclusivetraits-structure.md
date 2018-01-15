---
title: "SRWLockExclusiveTraits 구조체 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits
dev_langs: C++
helpviewer_keywords: SRWLockExclusiveTraits structure
ms.assetid: 38a996ef-c2d7-4886-b413-a426ecee8f05
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 05e7b2a6814cefffee258909f4bab11fcfe34f1c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="srwlockexclusivetraits-structure"></a>SRWLockExclusiveTraits 구조체
배타적 잠금 모드의 SRWLock 클래스의 일반적인 특성에 설명합니다.  
  
## <a name="syntax"></a>구문  
  
```  
struct SRWLockExclusiveTraits;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|`Type`|에 대 한 포인터에 대 한 동의어는 [SRWLOCK](../windows/srwlock-class.md) 클래스입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[SRWLockExclusiveTraits::GetInvalidValue 메서드](../windows/srwlockexclusivetraits-getinvalidvalue-method.md)|항상 유효 하지 않은 SRWLockExclusiveTraits 개체를 검색 합니다.|  
|[SRWLockExclusiveTraits::Unlock 메서드](../windows/srwlockexclusivetraits-unlock-method.md)|지정된 된 SRWLock 개체의 한 독점적인 제어권을 해제합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `SRWLockExclusiveTraits`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL::Wrappers::HandleTraits 네임스페이스](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)