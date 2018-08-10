---
title: 'Module:: getactivationfactory 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::GetActivationFactory
dev_langs:
- C++
helpviewer_keywords:
- GetActivationFactory method
ms.assetid: 59da8844-072e-414b-b89c-1db1cc4fd81d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f6fda1c514b6cb3e60a55d35323bf8b116f850ac
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40011870"
---
# <a name="modulegetactivationfactory-method"></a>Module::GetActivationFactory 메서드
모듈에 대한 활성화 팩터리를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
WRL_NOTHROW HRESULT GetActivationFactory(  
   _In_ HSTRING pActivatibleClassId,  
   _Deref_out_ IActivationFactory **ppIFactory,  
   wchar_t* serverName = nullptr  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 *pActivatibleClassId*  
 런타임 클래스의 IID입니다.  
  
 *ppIFactory*  
 지정된 런타임 클래스에 대한 IActivationFactory입니다.  
  
 *서버 이름*  
 현재 모듈의 클래스 팩터리 하위 집합 이름입니다. 에 사용 되는 서버 이름을 지정 합니다 [ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md) 매크로 지정 하거나 **nullptr** 기본 서버 이름을 가져올 수 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공하면 S_OK이고, 그렇지 않으면 GetActivationFactory에서 반환된 HRESULT입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [Module 클래스](../windows/module-class.md)  
 [ActivatableClass 매크로](../windows/activatableclass-macros.md)