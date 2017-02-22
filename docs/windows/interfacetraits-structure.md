---
title: "InterfaceTraits 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::InterfaceTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "InterfaceTraits 구조체"
ms.assetid: ede0c284-19a7-4892-9738-ff3da4923d0a
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# InterfaceTraits 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라구조체를 지원하고 코드에서 직접적으로 사용되는 것을 의도하지 않습니다.  
  
## 구문  
  
```  
template<  
   typename I0  
>  
struct __declspec(novtable) InterfaceTraits;  
  
template<  
   typename CloakedType  
>  
struct __declspec(novtable) InterfaceTraits<CloakedIid<CloakedType>>;  
  
template<>  
struct __declspec(novtable) InterfaceTraits<Nil>;  
```  
  
#### 매개 변수  
 `I0`  
 인터페이스의 이름입니다.  
  
 `CloakedType`  
 RuntimeClass, 구현 및 ChainInterfaces의 경우, 목록에 있는 인터페이스 인터페이스 Id를 지원합니다.  
  
## 설명  
 인터페이스의 일반적인 특성을 구현합니다.  
  
 두 번째 템플릿은 인터페이스의 숨겨진 특수화입니다.  서식 파일 3 Nil 매개 변수에 대한 특수화입니다.  
  
## 멤버  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|`Base`|`I0` 템플릿 매개변수에 대한 동의어.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[InterfaceTraits::CanCastTo 메서드](../windows/interfacetraits-cancastto-method.md)|지정된 포인터는 `Base` 에 대한 포인터를 캐스팅할 수 있는지에 대한 여부를 설명합니다.|  
|[InterfaceTraits::CastToBase 메서드](../windows/interfacetraits-casttobase-method.md)|지정된 된 포인터에 대한 포인터로 캐스팅 `Base`.|  
|[InterfaceTraits::CastToUnknown 메서드](../windows/interfacetraits-casttounknown-method.md)|지정된 포인터에 대한 IUnknown 포인터로 캐스팅 .|  
|[InterfaceTraits::FillArrayWithIid 메서드](../windows/interfacetraits-fillarraywithiid-method.md)|`Base` 의 인터페이스 ID를 인덱스 요소로 지정된 배열 요소에 할당합니다.|  
|[InterfaceTraits::Verify 메서드](../windows/interfacetraits-verify-method.md)|기본이 적절하게 도출되었는지 확인합니다.|  
  
### 공용 상수  
  
|Name|설명|  
|----------|--------|  
|[InterfaceTraits::IidCount 상수](../windows/interfacetraits-iidcount-constant.md)|인터페이스는 현재 InterfaceTraits 개체와 연결된 Id 번호가 들어있습니다.|  
  
## 상속 계층  
 `InterfaceTraits`  
  
## 요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스**Microsoft::WRL::Details  
  
## 참고 항목  
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)