---
title: "EnableIf 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "internal/Microsoft::WRL::Details::EnableIf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "EnableIf 구조체"
ms.assetid: 7825b283-e6b2-4f39-a4b9-c03bcd431b8e
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# EnableIf 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라구조체를 지원하고 코드에서 직접적으로 사용되는 것을 의도하지 않습니다.  
  
## 구문  
  
```  
template <  
   bool b,  
   typename T = void  
>  
  
struct EnableIf;  
template <  
   typename T  
>  
struct EnableIf<true, T>;  
```  
  
#### 매개 변수  
 `T`  
 A 형식  
  
 `b`  
 Boolean 식입니다.  
  
## 설명  
 두 번째 템플릿 매개변수에 의해 지정된 형식의 데이터 멤버를 정의합니다. 만일 첫 번째 템플릿 매개변수가 `true` 로 평가될 경우입니다.  
  
## 멤버  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|`type`|템플릿 매개변수 `b` 는 `true` 를 평가할 경우, 부분 특수화는 데이터 멤버 `type` 을 `T` 의 형식이 되도록 정의합니다.|  
  
## 상속 계층  
 `EnableIf`  
  
## 요구 사항  
 **헤더:**  internal.h  
  
 **네임스페이스:** Microsoft::WRL::Details  
  
## 참고 항목  
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)