---
title: "InterfaceTraits::FillArrayWithIid 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::InterfaceTraits::FillArrayWithIid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "FillArrayWithIid 메서드"
ms.assetid: 73583177-adc9-4fcb-917d-fa7e6d07c990
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# InterfaceTraits::FillArrayWithIid 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라구조체를 지원하고 코드에서 직접적으로 사용되는 것을 의도하지 않습니다.  
  
## 구문  
  
```  
__forceinline static void FillArrayWithIid(  
   _Inout_ unsigned long &index,  
   _In_ IID* iids  
);  
  
```  
  
#### 매개 변수  
 `index`  
 인덱스 값이 있는 필드에 대한 포인터입니다.  
  
 `iids`  
 인터페이스 ID의 배열입니다.  
  
## 설명  
 `Base` 의 인터페이스 ID를 인덱스 요소로 지정된 배열 요소에 할당합니다.  
  
 이 API의 이름, 반대로 하나의 배열 요소 수정 됩니다. 전체 배열 되지 않습니다.  
  
 `Base` 에 대한 더 자세한 내용은 Public Typedefs 섹션 [InterfaceTraits 구조체](../windows/interfacetraits-structure.md)를 참조하십시오.  
  
## 요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스:** Microsoft::WRL::Details  
  
## 참고 항목  
 [InterfaceTraits 구조체](../windows/interfacetraits-structure.md)   
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)