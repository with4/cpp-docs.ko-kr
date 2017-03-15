---
title: "ActivationFactory 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::ActivationFactory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActivationFactory 클래스"
ms.assetid: 5faddf1f-43b6-4f8a-97de-8c9d3ae1e1ff
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# ActivationFactory 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

하나 이상의 클래스를 Windows 런타임에 활성화 할 수 있습니다.  
  
## 구문  
  
```  
template <  
   typename I0 = Details::Nil,  
   typename I1 = Details::Nil,  
   typename I2 = Details::Nil  
>  
class ActivationFactory : public Details::RuntimeClass<typename Details::InterfaceListHelper<IActivationFactory, I0, I1, I2, Details::Nil>::TypeT, RuntimeClassFlags<WinRt | InhibitWeakReference>, false>;  
```  
  
#### 매개 변수  
 `I0`  
 0번째 인터페이스 입니다.  
  
 `I1`  
 첫 번째 인터페이스입니다.  
  
 `I2`  
 두 번째 인터페이스입니다.  
  
## 설명  
 ActivationFactory 등록 메서드 및 IActivationFactory 인터페이스에 대한 기본 기능을 제공합니다.  ActivationFactory를 사용하면 사용자 지정 팩터리 구현을 제공할 수도 있습니다.  
  
 다음 코드 조각에 기호로 ActivationFactory를 사용하는 방법을 보여 줍니다.  
  
 [!code-cpp[wrl-microsoft__wrl__activationfactory#1](../windows/codesnippet/CPP/activationfactory-class_1.cpp)]  
  
 다음 코드 조각은 [구현](../windows/implements-structure.md) 구조체를 더 많은 세개의 인터페이스 ID를 지정하기 위해 어떻게 사용되는 지 보여줍니다.  
  
 `struct MyFactory : ActivationFactory<Implements<I1, I2, I3>, I4, I5>;`  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[ActivationFactory::ActivationFactory 생성자](../windows/activationfactory-activationfactory-constructor.md)|ActivationFactory 클래를 초기화합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[ActivationFactory::AddRef 메서드](../windows/activationfactory-addref-method.md)|현재 ActivationFactory 개체의 참조 횟수를 증가시킵니다.|  
|[ActivationFactory::GetIids 메서드](../windows/activationfactory-getiids-method.md)|구현된 인터페이스 Id의 배열을 검색합니다.|  
|[ActivationFactory::GetRuntimeClassName 메서드](../windows/activationfactory-getruntimeclassname-method.md)|현재 ActivationFactory 인스턴스화하는 개체의 런타임 클래스 이름을 가져옵니다.|  
|[ActivationFactory::GetTrustLevel 메서드](../windows/activationfactory-gettrustlevel-method.md)|현재 ActivationFactory 인스턴스화하는 개체의 신뢰 수준을 가져옵니다.|  
|[ActivationFactory::QueryInterface 메서드](../windows/activationfactory-queryinterface-method.md)|지정한 인터페이스에 대한 포인터를 검색합니다.|  
|[ActivationFactory::Release 메서드](../windows/activationfactory-release-method.md)|현재 ActivationFactory 개체의 참조 횟수를 감소시킵니다.|  
  
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
  
## 요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)