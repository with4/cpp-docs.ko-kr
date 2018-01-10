---
title: "CriticalSectionTraits 구조체 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits
dev_langs: C++
helpviewer_keywords: CriticalSectionTraits structure
ms.assetid: c515a1b5-4eb0-40bc-9035-c4d9352c9de7
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c24d8dea31a87094329276af3ebfaf9f06136adc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="criticalsectiontraits-structure"></a>CriticalSectionTraits 구조체
잘못 된 임계 또는 중요 한 섹션을 해제 하는 함수를 지원 하기 위해 CriticalSection 개체를 특수화입니다.  
  
## <a name="syntax"></a>구문  
  
```  
struct CriticalSectionTraits;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|`Type`|A `typedef` 임계 영역에 대 한 포인터를 정의 하 합니다. `Type`로 정의 `typedef CRITICAL_SECTION* Type;`합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CriticalSectionTraits::GetInvalidValue 메서드](../windows/criticalsectiontraits-getinvalidvalue-method.md)|서식 파일 항상 유효 하지 않은 있도록 CriticalSection 템플릿을 특수화 합니다.|  
|[CriticalSectionTraits::Unlock 메서드](../windows/criticalsectiontraits-unlock-method.md)|지정 된 임계 영역 개체의 해제 소유권 지원 되도록 CriticalSection 템플릿을 특수화입니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `CriticalSectionTraits`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL::Wrappers::HandleTraits 네임스페이스](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)