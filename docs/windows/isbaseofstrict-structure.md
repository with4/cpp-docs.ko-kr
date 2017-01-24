---
title: "IsBaseOfStrict 구조체 | Microsoft Docs"
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
  - "internal/Microsoft::WRL::Details::IsBaseOfStrict"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IsBaseOfStrict 구조체"
ms.assetid: 6fed7366-c8d4-4991-b4fb-43ed93f8e1bf
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IsBaseOfStrict 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## 구문  
  
```  
template <  
   typename Base,  
   typename Derived  
>  
  
struct IsBaseOfStrict;  
template <  
   typename Base  
>  
struct IsBaseOfStrict<Base, Base>;  
```  
  
#### 매개 변수  
 `Base`  
 기본 형식입니다.  
  
 `Derived`  
 모든 파생된 형식  
  
## 설명  
 다른 기본 형식 인지를 테스트합니다.  
  
 산출할 수 있는 기본 형식에서 **true** 또는 **false** 을 파생된 형식이 있는지 테스트 하는 첫 번째 서식 파일입니다.  두 번째 서식 파일 형식에서 **false** 이 파생된 자체를 항상 하는 여부를 테스트합니다  
  
## 멤버  
  
### 공용 상수  
  
|Name|설명|  
|----------|--------|  
|[IsBaseOfStrict::value 상수](../windows/isbaseofstrict-value-constant.md)|다른 기본 형식 인지 나타냅니다.|  
  
## 상속 계층  
 `IsBaseOfStrict`  
  
## 요구 사항  
 **헤더:**  internal.h  
  
 **네임스페이스**Microsoft::WRL::Details  
  
## 참고 항목  
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)