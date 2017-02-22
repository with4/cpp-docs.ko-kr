---
title: "ClassFactory 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::ClassFactory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ClassFactory 클래스"
ms.assetid: f13e6bce-722b-4f18-b7cf-3ffa6345c1db
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# ClassFactory 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

IClassFactory 인터페이스의 키프레임의 기본 기능을 구현합니다.  
  
## 구문  
  
```  
template <  
   typename I0 = Details::Nil,  
   typename I1 = Details::Nil,  
   typename I2 = Details::Nil  
>  
class ClassFactory : public Details::RuntimeClass<  
   typename Details::InterfaceListHelper<IClassFactory,   
   I0,   
   I1,   
   I2,   
   Details::Nil>::TypeT,   
   RuntimeClassFlags<ClassicCom | InhibitWeakReference>,   
      false>;  
```  
  
#### 매개 변수  
 `I0`  
 0번째 인터페이스 입니다.  
  
 `I1`  
 첫 번째 인터페이스입니다.  
  
 `I2`  
 두 번째 인터페이스입니다.  
  
## 설명  
 사용자\-정의 팩터리 구현을 제공하기 위한 `ClassFactory` 를 사용합니다.  
  
 다음 프로그래밍 패턴은 어떻게 [구현](../windows/implements-structure.md) 구조체를 클래스 팩터리에서 세개 이상의 인터페이스를 지정하는 데 사용하는지를 보여줍니다.  
  
 `struct MyFactory : ClassFactory<Implements<I1, I2, I3>, I4, I5>`  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[ClassFactory::ClassFactory 생성자](../windows/classfactory-classfactory-constructor.md)||  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[ClassFactory::AddRef 메서드](../windows/classfactory-addref-method.md)|현재 ClassFactory 개체의 참조 횟수를 증가시킵니다.|  
|[ClassFactory::LockServer 메서드](../windows/classfactory-lockserver-method.md)|현재 클래스팩토리 개체에 의해 추적되는 근본적인 개체의 수를 증가시키거나 감소시킵니다.|  
|[ClassFactory::QueryInterface 메서드](../windows/classfactory-queryinterface-method.md)|매개 변수에 의해 지정된 인터페이스에 대한 포인터를 검색합니다.|  
|[ClassFactory::Release 메서드](../windows/classfactory-release-method.md)|현재 ClassFactory 개체의 참조 횟수를 감소시킵니다.|  
  
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
  
## 요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)   
 [RuntimeClassType 열거형](../windows/runtimeclasstype-enumeration.md)