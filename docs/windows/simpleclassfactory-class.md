---
title: SimpleClassFactory 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleClassFactory
dev_langs:
- C++
helpviewer_keywords:
- SimpleClassFactory class
ms.assetid: 6edda1b2-4e44-4e14-9364-72f519249962
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: debb78ba4be2731b8cffce1133518b0b4a04f63d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33892763"
---
# <a name="simpleclassfactory-class"></a>SimpleClassFactory 클래스
기본 클래스를 만드는 기본적인 메커니즘을 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<typename Base>  
class SimpleClassFactory : public ClassFactory<>;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `Base`  
 기본 클래스입니다.  
  
## <a name="remarks"></a>설명  
 기본 클래스 기본 생성자를 제공 해야 합니다.  
  
 다음 코드 예제와 SimpleClassFactory를 사용 하는 방법을 보여 줍니다는 [ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md) 매크로입니다.  
  
 `ActivatableClassWithFactoryEx(MyClass, SimpleClassFactory, MyServerName);`  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[SimpleClassFactory::CreateInstance 메서드](../windows/simpleclassfactory-createinstance-method.md)|지정된 된 인터페이스의 인스턴스를 만듭니다.|  
  
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
  
 `ClassFactory`  
  
 `SimpleClassFactory`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)