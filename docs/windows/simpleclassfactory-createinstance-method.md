---
title: 'Simpleclassfactory:: Createinstance 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleClassFactory::CreateInstance
dev_langs:
- C++
helpviewer_keywords:
- CreateInstance method
ms.assetid: 17b7947a-2608-49d9-b730-fef76501c9bc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8a31d364a6464962b8243cfaced03131a20f9324
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="simpleclassfactorycreateinstance-method"></a>SimpleClassFactory::CreateInstance 메서드

지정된 된 인터페이스의 인스턴스를 만듭니다.

## <a name="syntax"></a>구문

```cpp
STDMETHOD( CreateInstance )(
   _Inout_opt_ IUnknown* pUnkOuter,
   REFIID riid,
   _Deref_out_ void** ppvObject
);
```

### <a name="parameters"></a>매개 변수

*pUnkOuter*  
해야 `nullptr`, 그렇지 않으면 반환 값은 CLASS_E_NOAGGREGATION 합니다.

SimpleClassFactory 집계를 지원 하지 않습니다. 집계 된 지원 하 고 생성 되는 개체는 집계의 일부 였던 경우 `pUnkOuter` 집계의 IUnknown 인터페이스 제어에 대 한 포인터는 것입니다.

*riid*  
인터페이스를 만드는 개체의 ID입니다.

*ppvObject*  
이 작업이 완료 될 때, 지정 된 개체의 인스턴스로에 대 한 포인터는 `riid` 매개 변수입니다.

## <a name="return-value"></a>반환 값

성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.

## <a name="remarks"></a>설명

경우 &#95; &#95;WRL_STRICT&#95; &#95; 은 정의 assert 오류가 면 내보내집니다 클래스 템플릿 매개 변수에서 지정 된 기본 클래스에서 파생 되지 않습니다 [RuntimeClass](../windows/runtimeclass-class.md)는 ClassicCom를 사용 하 여 구성 되지 않았습니다 또는 또는 WinRtClassicComMix [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) 열거형 값입니다.

## <a name="requirements"></a>요구 사항

**헤더:** module.h

**네임스페이스:** Microsoft::WRL

## <a name="see-also"></a>참고 항목

[SimpleClassFactory 클래스](../windows/simpleclassfactory-class.md)