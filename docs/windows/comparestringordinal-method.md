---
title: "CompareStringOrdinal 메서드 | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::Details::CompareStringOrdinal"
dev_langs: 
  - "C++"
ms.assetid: ffa997fd-8cd7-40a5-b9e7-f55d40b072f4
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CompareStringOrdinal 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라구조체를 지원하고 코드에서 직접적으로 사용되는 것을 의도하지 않습니다.  
  
## 구문  
  
```cpp  
  
inline INT32 CompareStringOrdinal(  
   HSTRING lhs,   
   HSTRING rhs)  
```  
  
#### 매개 변수  
 `lhs`  
 비교할 첫째 HSTRING입니다.  
  
 `rhs`  
 비교할 둘째 HSTRING입니다.  
  
## 반환 값  
  
|값|조건|  
|-------|--------|  
|\-1|`lhs`가 `rhs`보다 작은 경우|  
|0|`lhs`가 `rhs`와 같습니다.|  
|1|`lhs`가 `rhs`보다 큰 경우|  
  
## 설명  
 지정된 두 HSTRING 개체를 비교하고 정렬 순서에서 두 개체의 상대 위치를 나타내는 정수를 반환합니다.  
  
## 요구 사항  
 **헤더:** corewrappers.h  
  
 **네임스페이스:** Microsoft::WRL::Wrappers::Details  
  
## 참고 항목  
 [Microsoft::WRL::Wrappers::Details 네임스페이스](../windows/microsoft-wrl-wrappers-details-namespace.md)