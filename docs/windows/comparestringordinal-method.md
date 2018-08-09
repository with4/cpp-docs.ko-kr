---
title: CompareStringOrdinal 메서드 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::CompareStringOrdinal
dev_langs:
- C++
ms.assetid: ffa997fd-8cd7-40a5-b9e7-f55d40b072f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7084b16536533c9605b741adb596a2a7d383c153
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39650000"
---
# <a name="comparestringordinal-method"></a>CompareStringOrdinal 메서드
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
inline INT32 CompareStringOrdinal(  
   HSTRING lhs,   
   HSTRING rhs)  
```  
  
### <a name="parameters"></a>매개 변수  
 *lhs*  
 비교할 첫 번째 HSTRING입니다.  
  
 *rhs*  
 비교할 두 번째 HSTRING입니다.  
  
## <a name="return-value"></a>반환 값  
  
|값|조건|  
|-----------|---------------|  
|-1|*lhs* 는 보다 작은 *rhs*합니다.|  
|0|*lhs* equals *rhs*합니다.|  
|1|*lhs* 보다 크면 *rhs*합니다.|  
  
## <a name="remarks"></a>설명  
 두 지정 된 HSTRING 개체를 비교 하 고 정렬 순서에서 상대 위치를 나타내는 정수를 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL::Wrappers::Details 네임스페이스](../windows/microsoft-wrl-wrappers-details-namespace.md)