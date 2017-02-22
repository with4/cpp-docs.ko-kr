---
title: "Implements 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Implements"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Implements 구조체"
ms.assetid: 29b13e90-34d4-4a0b-babd-5187c9eb0c36
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Implements 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정된 인터페이스에 대해 QueryInterface 및 GetIid를 구현합니다.  
  
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
struct __declspec(novtable) Implements : Details::ImplementsHelper<RuntimeClassFlags<WinRt>, typename Details::InterfaceListHelper<I0, I1, I2, I3, I4, I5, I6, I7, I8, I9>::TypeT>, Details::ImplementsBase;  
template <  
   int flags,  
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
struct __declspec(novtable) Implements<RuntimeClassFlags<flags>, I0, I1, I2, I3, I4, I5, I6, I7, I8> : Details::ImplementsHelper<RuntimeClassFlags<flags>, typename Details::InterfaceListHelper<I0, I1, I2, I3, I4, I5, I6, I7, I8>::TypeT>, Details::ImplementsBase;  
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
  
 `flags`  
 클래스에 대한 플래그를 구성합니다.  [런타임클래스플래그](../windows/runtimeclassflags-structure.md) 구조체로 지정된 하나 또는 그 이상의 [런타임클래스형식](../windows/runtimeclasstype-enumeration.md) 열거형입니다.  
  
## 설명  
 지정된 인터페이스 목록에서 파생되고 QueryInterface 및 GetIid 도우미 템플릿 구현 합니다.  
  
 `I9` 인터페이스 매개변수를 통한 `I0` 는 IUnknown, 또는 [ChainInterfaces](../windows/chaininterfaces-structure.md) 템플릿 으로부터 도출되야만 합니다.  `flags` 매개 변수를 IInspectable 또는 IUnknown에 대한 지원을 생성할지 여부를 결정 합니다.  
  
## 멤버  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|`ClassFlags`|이 `RuntimeClassFlags<WinRt>` 의 동의어입니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[Implements::CanCastTo 메서드](../windows/implements-cancastto-method.md)|지정한 인터페이스에 대한 포인터를 검색합니다.|  
|[Implements::CastToUnknown 메서드](../windows/implements-casttounknown-method.md)|근본적인 IUnknown 인터페이스에 대한 포인터입니다.|  
|[Implements::FillArrayWithIid 메서드](../windows/implements-fillarraywithiid-method.md)|지정된 배열의 요소를 현재 zeroth 템플릿 매개 변수로 지정 된 인터페이스 ID를 삽입 합니다.|  
  
### 보호 된 상수  
  
|Name|설명|  
|----------|--------|  
|[Implements::IidCount 상수](../windows/implements-iidcount-constant.md)|구현된 인터페이스 ID 저장합니다.|  
  
## 상속 계층  
 `I0`  
  
 `ChainInterfaces`  
  
 `I0`  
  
 `ImplementsBase`  
  
 `ImplementsHelper`  
  
 `Implements`  
  
## 요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)