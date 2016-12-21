---
title: "DerefHelper 구조체 | Microsoft Docs"
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
  - "async/Microsoft::WRL::Details::DerefHelper"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DerefHelper 구조체"
ms.assetid: 86ded58b-c3ee-4a4f-bb86-4f67b895d427
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# DerefHelper 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라구조체를 지원하고 코드에서 직접적으로 사용되는 것을 의도하지 않습니다.  
  
## 구문  
  
```  
template <  
   typename T  
>  
struct DerefHelper;  
  
template <  
   typename T  
>  
struct DerefHelper<T*>;  
```  
  
#### 매개 변수  
 `T`  
 템플릿 매개 변수  
  
## 설명  
 역참조된 포인터는 `T*` 템플릿 매개 변수를 표현합니다.  
  
 DerefHelper과 같은 식에서 사용 됩니다: 예를 들어 `ComPtr<Details::DerefHelper<ProgressTraits::Arg1Type>::DerefType> operationInterface;`.  
  
## 멤버  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|`DerefType`|역참조된 템플릿 매개 변수 식별자 `T*`를 식별합니다.|  
  
## 상속 계층  
 `DerefHelper`  
  
## 요구 사항  
 **헤더:** async.h  
  
 **네임스페이스**Microsoft::WRL::Details  
  
## 참고 항목  
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)