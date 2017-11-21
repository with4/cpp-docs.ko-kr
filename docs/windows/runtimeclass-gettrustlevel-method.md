---
title: "Runtimeclass:: Gettrustlevel 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::RuntimeClass::GetTrustLevel
dev_langs: C++
helpviewer_keywords: GetTrustLevel method
ms.assetid: bd90407e-6dd7-41c3-9ea0-c402c276014a
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: bf5125f7f0fdfe6309d668404dd1077e629a4fac
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="runtimeclassgettrustlevel-method"></a>RuntimeClass::GetTrustLevel 메서드

현재 RuntimeClass 개체의 신뢰 수준을 가져옵니다.

## <a name="syntax"></a>구문

```cpp
STDMETHOD(GetTrustLevel)(
    _Out_ TrustLevel* trustLvl
);
```

### <a name="parameters"></a>매개 변수

*trustLvl*  
이 작업이 완료 될 때 현재 RuntimeClass 개체의 신뢰 수준입니다.

## <a name="return-value"></a>반환 값

항상 S_OK입니다.

## <a name="remarks"></a>설명

어설션 오류는 내보낸된 if / #95; &#95; WRL_STRICT &#95; #95 또는 &#95; &#95; WRL_FORCE_INSPECTABLE_CLASS_MACRO &#95; #95 정의 되지 않았습니다.

## <a name="requirements"></a>요구 사항

**헤더:** implements.h

**네임스페이스:** Microsoft::WRL

## <a name="see-also"></a>참고 항목

[RuntimeClass 클래스](../windows/runtimeclass-class.md)