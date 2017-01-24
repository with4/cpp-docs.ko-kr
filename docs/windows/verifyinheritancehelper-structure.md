---
title: "VerifyInheritanceHelper 구조체 | Microsoft Docs"
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
  - "implements/Microsoft::WRL::Details::VerifyInheritanceHelper"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VerifyInheritanceHelper 구조체"
ms.assetid: 8a48a702-0f71-4807-935b-8311f0a7a8b6
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# VerifyInheritanceHelper 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## 구문  
  
```  
template <  
   typename I,  
   typename Base  
>  
struct VerifyInheritanceHelper;  
template <  
   typename I  
>  
struct VerifyInheritanceHelper<I, Nil>;  
```  
  
#### 매개 변수  
 `I`  
 A 형식  
  
 `Base`  
 또 다른 유형입니다.  
  
## 설명  
 하나의 인터페이스가 다른 인터페이스에서 파생 되는지 여부를 테스트 합니다.  
  
## 멤버  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[VerifyInheritanceHelper::Verify 메서드](../windows/verifyinheritancehelper-verify-method.md)|현재 템플릿 매개 변수에 의해 지정된 두 개의 인터페이스를 테스트하고 하나의 인터페이스에서 파생되었는지 여부를 결정합니다.|  
  
## 상속 계층  
 `VerifyInheritanceHelper`  
  
## 요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스**Microsoft::WRL::Details  
  
## 참고 항목  
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)