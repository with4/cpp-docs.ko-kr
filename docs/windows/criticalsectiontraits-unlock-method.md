---
title: 'Criticalsectiontraits:: Unlock 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::Unlock
dev_langs:
- C++
helpviewer_keywords:
- Unlock method
ms.assetid: 8fb382f5-6eda-407e-9673-71d77bda4962
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2f66f185692c200ea459b88363143c0cc1af9d55
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39466012"
---
# <a name="criticalsectiontraitsunlock-method"></a>CriticalSectionTraits::Unlock 메서드
지정 된 임계 영역 개체의 해제 소유권을 지원 하도록 해당 CriticalSection 템플릿으로 전문으로 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
inline static void Unlock(  
   _In_ Type cs  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 *cs*  
 임계 영역 개체에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 합니다 *형식* 한정자로 정의 된 `typedef CRITICAL_SECTION* Type;`합니다.  
  
 자세한 내용은 Windows API 설명서의 "동기화 함수" 섹션에서 "LeaveCriticalSection function"입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>참고 항목  
 [CriticalSectionTraits 구조체](../windows/criticalsectiontraits-structure.md)