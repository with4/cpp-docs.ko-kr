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
ms.openlocfilehash: e3abf87340671d1ac4851b055a57896e340d0c20
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33860813"
---
# <a name="comparestringordinal-method"></a>CompareStringOrdinal 메서드
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
inline INT32 CompareStringOrdinal(  
   HSTRING lhs,   
   HSTRING rhs)  
```  
  
#### <a name="parameters"></a>매개 변수  
 `lhs`  
 비교할 첫 번째 HSTRING 합니다.  
  
 `rhs`  
 비교할 두 번째 HSTRING 합니다.  
  
## <a name="return-value"></a>반환 값  
  
|값|조건|  
|-----------|---------------|  
|-1|`lhs`가 `rhs`보다 작은 경우|  
|0|`lhs`가 `rhs`와 같습니다.|  
|1|`lhs`가 `rhs`보다 큰 경우|  
  
## <a name="remarks"></a>설명  
 지정 된 두 HSTRING 개체 하 고 정렬 순서에서의 상대 위치를 나타내는 정수를 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL::Wrappers::Details 네임스페이스](../windows/microsoft-wrl-wrappers-details-namespace.md)