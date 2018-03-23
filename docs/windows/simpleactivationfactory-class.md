---
title: SimpleActivationFactory 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleActivationFactory
dev_langs:
- C++
helpviewer_keywords:
- SimpleActivationFactory class
ms.assetid: aff768e0-0038-4fd7-95d2-ad7d308da41c
caps.latest.revision: ''
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0f6aabaae1e19fef3631e372391c81108f212c90
ms.sourcegitcommit: 1d11412c8f5e6ddf4edded89e0ef5097cc89f812
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2018
---
# <a name="simpleactivationfactory-class"></a>SimpleActivationFactory 클래스
Windows 런타임 또는 클래식 COM 기본 클래스를 만드는 기본적인 메커니즘을 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<typename Base>  
class SimpleActivationFactory : public ActivationFactory<>;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `Base`  
 기본 클래스입니다.  
  
## <a name="remarks"></a>설명  
 기본 클래스 기본 생성자를 제공 해야 합니다.  
  
 다음 코드 예제와 SimpleActivationFactory를 사용 하는 방법을 보여 줍니다는 [ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md) 매크로입니다.  
  
 `ActivatableClassWithFactoryEx(MyClass, SimpleActivationFactory, MyServerName);`  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[SimpleActivationFactory::ActivateInstance 메서드](../windows/simpleactivationfactory-activateinstance-method.md)|지정된 된 인터페이스의 인스턴스를 만듭니다.|  
|[SimpleActivationFactory::GetRuntimeClassName 메서드](../windows/simpleactivationfactory-getruntimeclassname-method.md)|런타임 클래스 이름에서 지정 된 클래스의 인스턴스를 가져옵니다는 `Base` 클래스 템플릿 매개 변수입니다.|  
|[SimpleActivationFactory::GetTrustLevel 메서드](../windows/simpleactivationfactory-gettrustlevel-method.md)|신뢰 수준에서 지정 된 클래스의 인스턴스를 가져옵니다는 `Base` 클래스 템플릿 매개 변수입니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `I0`  
  
 `ChainInterfaces`  
  
 `I0`  
  
 `RuntimeClassBase`  
  
 `ImplementsHelper`  
  
 `DontUseNewUseMake`  
  
 `RuntimeClassFlags`  
  
 `RuntimeClassBaseT`  
  
 `RuntimeClass`  
  
 `ActivationFactory`  
  
 `SimpleActivationFactory`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)