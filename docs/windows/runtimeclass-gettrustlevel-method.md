---
title: 'Runtimeclass:: Gettrustlevel 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClass::GetTrustLevel
dev_langs:
- C++
helpviewer_keywords:
- GetTrustLevel method
ms.assetid: bd90407e-6dd7-41c3-9ea0-c402c276014a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: adcec3f4a531a6c48e0995468994900124746e4b
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40015133"
---
# <a name="runtimeclassgettrustlevel-method"></a>RuntimeClass::GetTrustLevel 메서드

현재 신뢰 수준을 가져옵니다 **RuntimeClass** 개체입니다.

## <a name="syntax"></a>구문

```cpp
STDMETHOD(GetTrustLevel)(
    _Out_ TrustLevel* trustLvl
);
```

### <a name="parameters"></a>매개 변수
*trustLvl*  
이 작업이 완료 되 면, 현재 신뢰 수준 **RuntimeClass** 개체입니다.

## <a name="return-value"></a>반환 값

항상 S_OK입니다.

## <a name="remarks"></a>설명

어설션 오류가 발생 하는 경우에 내보내집니다 `__WRL_STRICT__` 또는 `__WRL_FORCE_INSPECTABLE_CLASS_MACRO__` 정의 되어 있지 않습니다.

## <a name="requirements"></a>요구 사항

**헤더:** implements.h

**네임스페이스:** Microsoft::WRL

## <a name="see-also"></a>참고 항목
 [RuntimeClass 클래스](../windows/runtimeclass-class.md)