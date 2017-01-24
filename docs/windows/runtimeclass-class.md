---
title: "RuntimeClass 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::RuntimeClass"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RuntimeClass 클래스"
ms.assetid: d52f9d1a-98e5-41f2-a143-8fb629dd0727
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# RuntimeClass 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정된 수의 인터페이스를 상속하고 지정된 제공하는 인스턴스화된 클래스를 나타내는 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)], 기본 COM 및 약한 참조를 지원합니다.  
  
 `RuntimeClass` 클래스는 `AddRef`, `Release` 및 `QueryInterface`를 구현하고 모듈의 전체 참조 개수를 관리하는 데 활용하므로 일반적으로 이 클래스에서 WRL 형식을 파생합니다.  
  
## 구문  
  
```  
template <  
   typename I0,  
   typename I1 = Details::Nil,  
   typename I2 = Details::Nil,  
   typename I3 = Details::Nil,  
   typename I4 = Details::Nil,  
   typename I5 = Details::Nil,  
   typename I6 = Details::Nil,  
   typename I7 = Details::Nil,  
   typename I8 = Details::Nil,  
   typename I9 = Details::Nil  
>  
class RuntimeClass : public Details::RuntimeClass<typename Details::InterfaceListHelper<I0, I1, I2, I3, I4, I5, I6, I7, I8, I9>::TypeT, RuntimeClassFlags<WinRt>>;  
  
template <  
   unsigned int classFlags,  
   typename I0,  
   typename I1,  
   typename I2,  
   typename I3,  
   typename I4,  
   typename I5,  
   typename I6,  
   typename I7,  
   typename I8  
>  
class RuntimeClass<RuntimeClassFlags<classFlags>, I0, I1, I2, I3, I4, I5, I6, I7, I8> : public Details::RuntimeClass<typename Details::InterfaceListHelper<I0, I1, I2, I3, I4, I5, I6, I7, I8>::TypeT, RuntimeClassFlags<classFlags> >;  
```  
  
#### 매개 변수  
 `I0`  
 0번째 인터페이스 ID입니다. \(필수\)  
  
 `I1`  
 첫 번째 인터페이스 ID입니다. \(옵션\)  
  
 `I2`  
 두 번째 인터페이스 ID입니다. \(옵션\)  
  
 `I3`  
 세 번째 인터페이스 ID입니다. \(옵션\)  
  
 `I4`  
 네 번째 인터페이스 ID입니다. \(옵션\)  
  
 `I5`  
 다섯 번째 인터페이스 ID입니다. \(옵션\)  
  
 `I6`  
 여섯 번째 인터페이스 ID입니다. \(옵션\)  
  
 `I7`  
 일곱 번째 인터페이스 ID입니다. \(옵션\)  
  
 `I8`  
 여덟 번째 인터페이스 ID입니다. \(옵션\)  
  
 `I9`  
 아홉 번째 인터페이스 ID입니다. \(옵션\)  
  
 `classFlags`  
 하나 이상의 [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) 열거형 값의 조합입니다.  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[RuntimeClass::RuntimeClass 생성자](../windows/runtimeclass-runtimeclass-constructor.md)|RuntimeClass 클래스의 현재 인스턴스를 초기화합니다.|  
|[RuntimeClass::~RuntimeClass 소멸자](../windows/runtimeclass-tilde-runtimeclass-destructor.md)|RuntimeClass 클래스의 현재 인스턴스를 초기화 해제합니다.|  
  
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
  
 `RuntimeClass`  
  
## 요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)