---
title: CriticalSectionTraits 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits
dev_langs:
- C++
helpviewer_keywords:
- CriticalSectionTraits structure
ms.assetid: c515a1b5-4eb0-40bc-9035-c4d9352c9de7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8b10d130190308520771e37e97d34238f75670ad
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39466685"
---
# <a name="criticalsectiontraits-structure"></a>CriticalSectionTraits 구조체
잘못 된 임계 또는 중요 섹션을 해제 하는 함수를 지원 하기 위해 CriticalSection 개체를 전문으로 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
struct CriticalSectionTraits;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|`Type`|A **typedef** 임계 영역에 대 한 포인터를 정의 하는 합니다. `Type` 로 정의 된 `typedef CRITICAL_SECTION* Type;`합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CriticalSectionTraits::GetInvalidValue 메서드](../windows/criticalsectiontraits-getinvalidvalue-method.md)|전문적으로 다루는 `CriticalSection` 템플릿 서식 파일은 항상 유효한 수 있도록 합니다.|  
|[CriticalSectionTraits::Unlock 메서드](../windows/criticalsectiontraits-unlock-method.md)|특수화는 `CriticalSection` 를 지정 된 임계 영역 개체의 해제 소유권 지원 하므로 템플릿.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `CriticalSectionTraits`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL::Wrappers::HandleTraits 네임스페이스](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)