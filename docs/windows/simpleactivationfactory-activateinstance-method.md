---
title: 'Simpleactivationfactory:: Activateinstance 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleActivationFactory::ActivateInstance
dev_langs:
- C++
helpviewer_keywords:
- ActivateInstance method
ms.assetid: 4f836e51-5a6c-4bad-b871-9f25199298b4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fe1342c3927183ae5eec30c8dd0a40ee95f37277
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39646564"
---
# <a name="simpleactivationfactoryactivateinstance-method"></a>SimpleActivationFactory::ActivateInstance 메서드

지정된 된 인터페이스의 인스턴스를 만듭니다.

## <a name="syntax"></a>구문

```cpp
STDMETHOD( ActivateInstance )(
    _Deref_out_ IInspectable **ppvObject
);
```

### <a name="parameters"></a>매개 변수

*ppvObject*  
이 작업이 완료 될 때, 지정 된 개체의 인스턴스에 대 한 포인터를 `Base` 클래스 템플릿 매개 변수입니다.

## <a name="return-value"></a>반환 값

성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.

## <a name="remarks"></a>설명

경우 &#95; &#95;WRL_STRICT&#95; &#95; 가 정의 된 assert 오류가 내보내집니다 클래스 템플릿 매개 변수에서 지정 된 기본 클래스에서 파생 되지 않습니다 [RuntimeClass](../windows/runtimeclass-class.md), 않거나는 WinRt를 사용 하 여 구성 되지 않았습니다 또는 WinRtClassicComMix [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) 열거형 값입니다.

## <a name="requirements"></a>요구 사항

**헤더:** module.h

**네임스페이스:** Microsoft::WRL

## <a name="see-also"></a>참고 항목
 [SimpleActivationFactory 클래스](../windows/simpleactivationfactory-class.md)