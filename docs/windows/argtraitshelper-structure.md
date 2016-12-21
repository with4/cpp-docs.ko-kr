---
title: "ArgTraitsHelper 구조체 | Microsoft Docs"
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
  - "event/Microsoft::WRL::Details::ArgTraitsHelper"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ArgTraitsHelper 구조체"
ms.assetid: e3f798da-0aef-4a57-95d3-d38c34c47d72
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ArgTraitsHelper 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라구조체를 지원하고 코드에서 직접적으로 사용되는 것을 의도하지 않습니다.  
  
## 구문  
  
```  
template<  
   typename TDelegateInterface  
>  
struct ArgTraitsHelper;  
```  
  
#### 매개 변수  
 `TDelegateInterface`  
 대리자 인터페이스입니다.  
  
## 설명  
 대리자 인수의 공통적인 특성을 정의하는 것을 돕습니다.  
  
## 멤버  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|`methodType`|이 `decltype(&TDelegateInterface::Invoke)` 의 동의어입니다.|  
|`Traits`|이 `ArgTraits<methodType>` 의 동의어입니다.|  
  
### 공용 상수  
  
|Name|설명|  
|----------|--------|  
|[ArgTraitsHelper::args 상수](../windows/argtraitshelper-args-constant.md)|[ArgTraits::args](../windows/argtraits-args-constant.md) 를 대리자 인퍼페이스의 호출 메소드에서 매개변수의 수를 계산하는 것을 돕습니다.|  
  
## 상속 계층  
 `ArgTraitsHelper`  
  
## 요구 사항  
 **헤더:** event.h  
  
 **네임스페이스:** Microsoft::WRL::Details  
  
## 참고 항목  
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)