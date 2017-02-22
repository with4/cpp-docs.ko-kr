---
title: "Move 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "internal/Microsoft::WRL::Details::Move"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Move 함수"
ms.assetid: c9525426-97e8-4d8c-9877-b689d8a0dc67
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Move 함수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라구조체를 지원하고 코드에서 직접적으로 사용되는 것을 의도하지 않습니다.  
  
## 구문  
  
```  
template<  
   class T  
>  
inline typename RemoveReference<T>::Type&& Move(  
   _Inout_ T&& arg  
);  
```  
  
#### 매개 변수  
 `T`  
 인수의 형식입니다.  
  
 `arg`  
 이동 하는 인수입니다.  
  
## 반환 값  
 매개 변수 `arg` 특성 참조 또는 rvalue 참조 후, 제거 되었습니다.  
  
## 설명  
 지정된 인수를 다른 위치로 이동합니다.  
  
 자세한 내용은 **의미체계 이동** 섹션인 [Rvalue 참조 선언자: &&](../cpp/rvalue-reference-declarator-amp-amp.md) 을 참조하십시오.  
  
## 요구 사항  
 **헤더:**  internal.h  
  
 **네임스페이스:** Microsoft::WRL::Details  
  
## 참고 항목  
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)