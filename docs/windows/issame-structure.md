---
title: "IsSame 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "internal/Microsoft::WRL::Details::IsSame"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IsSame 구조체"
ms.assetid: 1eddbc3f-3cc5-434f-8495-e4477e1f868e
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# IsSame 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## 구문  
  
```  
template <  
   typename T1,  
   typename T2  
>  
struct IsSame;  
template <  
   typename T1  
>  
struct IsSame<T1, T1>;  
```  
  
#### 매개 변수  
 `T1`  
 A 형식  
  
 `T2`  
 또 다른 유형입니다.  
  
## 설명  
 형식이 지정 된 것과 같습니다 다른 테스트 종류를 지정 합니다.  
  
## 멤버  
  
### 공용 상수  
  
|Name|설명|  
|----------|--------|  
|[IsSame::value 상수](../windows/issame-value-constant.md)|다른 동일한 형식 인지 여부를 나타냅니다.|  
  
## 상속 계층  
 `IsSame`  
  
## 요구 사항  
 **헤더:**  internal.h  
  
 **네임스페이스**Microsoft::WRL::Details  
  
## 참고 항목  
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)