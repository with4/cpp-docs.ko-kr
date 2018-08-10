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
ms.openlocfilehash: aa0d48ba96c550ff6ee1248dccd0b4c8e3021212
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40020306"
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
여야 **nullptr**고, 그렇지 않으면 반환 값은 CLASS_E_NOAGGREGATION 합니다.

SimpleClassFactory 집계를 지원 하지 않습니다. 집계 된 지원 하 고 생성 되는 개체, 집계의 일부 였던 *pUnkOuter* 에 대 한 포인터를 제어 하는 것 `IUnknown` 집계의 인터페이스입니다.

*riid*  
만들 개체의 ID를 인터페이스입니다.

*ppvObject*  
이 작업이 완료 될 때, 지정 된 개체의 인스턴스에 대 한 포인터를 *riid* 매개 변수입니다.

## <a name="return-value"></a>반환 값

성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.

## <a name="remarks"></a>설명

하는 경우 `__WRL_STRICT__` 가 정의 된 assert 오류가 내보내집니다 클래스 템플릿 매개 변수에서 지정 된 기본 클래스에서 파생 되지 않습니다 [RuntimeClass](../windows/runtimeclass-class.md), 않거나 ClassicCom 또는 WinRtClassicComMix 구성 되지 않았습니다 [ RuntimeClassType](../windows/runtimeclasstype-enumeration.md) 열거형 값입니다.

## <a name="requirements"></a>요구 사항

**헤더:** module.h

**네임스페이스:** Microsoft::WRL

## <a name="see-also"></a>참고 항목
 [SimpleClassFactory 클래스](../windows/simpleclassfactory-class.md)