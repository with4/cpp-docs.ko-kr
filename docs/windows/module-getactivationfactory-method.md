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
ms.openlocfilehash: 837cb68173ca1994de6bc560882d617bb3aa03e0
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33887015"
---
# <a name="modulegetactivationfactory-method"></a>Module::GetActivationFactory 메서드
모듈에 대한 활성화 팩터리를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
WRL_NOTHROW HRESULT GetActivationFactory(  
   _In_ HSTRING pActivatibleClassId,  
   _Deref_out_ IActivationFactory **ppIFactory,  
   wchar_t* serverName = nullptr  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pActivatibleClassId`  
 런타임 클래스의 IID입니다.  
  
 `ppIFactory`  
 지정된 런타임 클래스에 대한 IActivationFactory입니다.  
  
 `serverName`  
 현재 모듈의 클래스 팩터리 하위 집합 이름입니다. 사용 되는 서버 이름을 지정는 [ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md) 매크로 지정 하거나 `nullptr` 기본 서버 이름을 가져올 수 있습니다.  
  
## <a name="return-value"></a>반환 값  
 성공하면 S_OK이고, 그렇지 않으면 GetActivationFactory에서 반환된 HRESULT입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
[Module 클래스](../windows/module-class.md) [ActivatableClass 매크로](../windows/activatableclass-macros.md)