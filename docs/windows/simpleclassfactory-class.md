---
title: "SimpleClassFactory 클래스 | Microsoft Docs"
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
  - "module/Microsoft::WRL::SimpleClassFactory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SimpleClassFactory 클래스"
ms.assetid: 6edda1b2-4e44-4e14-9364-72f519249962
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SimpleClassFactory 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

기본 클래스를 만드는 기본적인 방법을 제공 합니다.  
  
## 구문  
  
```  
template<  
   typename Base  
>  
class SimpleClassFactory : public ClassFactory<>;  
```  
  
#### 매개 변수  
 `Base`  
 \(기본 클래스\)  
  
## 설명  
 이 기본 클래스에는 기본 생성자를 제공합니다.  
  
 다음 코드 예제에서는 SimpleClassFactory를 사용 하는 방법의 [ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md) 매크로를 시범보입니다.  
  
 `ActivatableClassWithFactoryEx(MyClass, SimpleClassFactory, MyServerName);`  
  
## 멤버  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[SimpleClassFactory::CreateInstance 메서드](../windows/simpleclassfactory-createinstance-method.md)|지정된 인터페이스의 인스턴스를 만듭니다.|  
  
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
  
 `ClassFactory`  
  
 `SimpleClassFactory`  
  
## 요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)