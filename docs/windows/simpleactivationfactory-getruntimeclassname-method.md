---
title: "Simpleactivationfactory:: Getruntimeclassname 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleActivationFactory::GetRuntimeClassName
dev_langs:
- C++
ms.assetid: 3aa07487-9a42-46f8-8893-37ba6315e50b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 73431c7a0f719579caf3df146b69dd8d7248d0a6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="simpleactivationfactorygetruntimeclassname-method"></a>SimpleActivationFactory::GetRuntimeClassName 메서드

런타임 클래스 이름에서 지정 된 클래스의 인스턴스를 가져옵니다는 `Base` 클래스 템플릿 매개 변수입니다.

## <a name="syntax"></a>구문

```cpp
STDMETHOD( GetRuntimeClassName )(
    _Out_ HSTRING* runtimeName
);
```

### <a name="parameters"></a>매개 변수

*runtimeName*  
이 작업이 완료 될 때, 런타임 클래스 이름이 있습니다.

## <a name="return-value"></a>반환 값

성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.

## <a name="remarks"></a>설명

경우 &#95; &#95; WRL_STRICT &#95; #95 정의 어설션 오류가 발생 하 여 지정 된 클래스가 `Base` 클래스 템플릿 매개 변수에서 파생 되지 않습니다 [RuntimeClass](../windows/runtimeclass-class.md), WinRt 또는 WinRtClassicComMix 구성 되지 않았습니다 또는 [ RuntimeClassType](../windows/runtimeclasstype-enumeration.md) 열거형 값입니다.

## <a name="requirements"></a>요구 사항

**헤더:** module.h

**네임스페이스:** Microsoft::WRL

## <a name="see-also"></a>참고 항목

[SimpleActivationFactory 클래스](../windows/simpleactivationfactory-class.md)