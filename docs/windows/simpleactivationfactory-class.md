---
title: "SimpleActivationFactory 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::SimpleActivationFactory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SimpleActivationFactory 클래스"
ms.assetid: aff768e0-0038-4fd7-95d2-ad7d308da41c
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SimpleActivationFactory 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Windows 런타임 또는 기본 COM 기본 클래스를 만드는 기본적인 방법을 제공 합니다.  
  
## 구문  
  
```  
template<  
   typename Base  
>  
class SimpleActivationFactory : public ActivationFactory<>;  
```  
  
#### 매개 변수  
 `Base`  
 \(기본 클래스\)  
  
## 설명  
 이 기본 클래스에는 기본 생성자를 제공합니다.  
  
 다음 코드 예제에서는 SimpleActivationFactory를 사용 하는 방법의 [ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md) 매크로를 시범보입니다.  
  
 `ActivatableClassWithFactoryEx(MyClass, SimpleActivationFactory, MyServerName);`  
  
## 멤버  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[SimpleActivationFactory::ActivateInstance 메서드](../windows/simpleactivationfactory-activateinstance-method.md)|지정된 인터페이스의 인스턴스를 만듭니다.|  
|[SimpleActivationFactory::GetRuntimeClassName 메서드](../windows/simpleactivationfactory-getruntimeclassname-method.md)|런타임 클래스 이름에 지정된 클래스의 인스턴스를 `Base` 클래스 탬플릿 매개변수에 의해 가져옵니다.|  
|[SimpleActivationFactory::GetTrustLevel 메서드](../windows/simpleactivationfactory-gettrustlevel-method.md)|`Base` 클래스 탬플릿 매개변수에 의해 지정된 클래스의 인스턴스 신뢰 수준을 가져옵니다.|  
  
## 상속 계층  
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
  
## 요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)