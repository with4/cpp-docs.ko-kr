---
title: 'Simpleactivationfactory:: Getruntimeclassname 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleActivationFactory::GetRuntimeClassName
dev_langs:
- C++
ms.assetid: 3aa07487-9a42-46f8-8893-37ba6315e50b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9c8bc1962e946a48b6ebebaf072e4cb32559a6de
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40014710"
---
# <a name="simpleactivationfactorygetruntimeclassname-method"></a>SimpleActivationFactory::GetRuntimeClassName 메서드

런타임 클래스 이름에서 지정한 클래스의 인스턴스를 가져옵니다는 `Base` 클래스 템플릿 매개 변수입니다.

## <a name="syntax"></a>구문

```cpp
STDMETHOD( GetRuntimeClassName )(
    _Out_ HSTRING* runtimeName
);
```

### <a name="parameters"></a>매개 변수
*runtimeName*  
이 작업이 완료 될 때 런타임 클래스 이름입니다.

## <a name="return-value"></a>반환 값

성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.

## <a name="remarks"></a>설명

경우 `__WRL_STRICT__` 는 정의 된 assert 오류가 내보내집니다으로 지정 된 클래스를 `Base` 클래스 템플릿 매개 변수에서 파생 되지 않습니다 [RuntimeClass](../windows/runtimeclass-class.md), 않거나 WinRt 또는 WinRtClassicComMix 를사용하여구성되지않았습니다[RuntimeClassType](../windows/runtimeclasstype-enumeration.md) 열거형 값입니다.

## <a name="requirements"></a>요구 사항

**헤더:** module.h

**네임스페이스:** Microsoft::WRL

## <a name="see-also"></a>참고 항목
 [SimpleActivationFactory 클래스](../windows/simpleactivationfactory-class.md)