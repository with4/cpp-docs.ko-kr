---
title: "InterfaceTraits::CastToUnknown 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::InterfaceTraits::CastToUnknown"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CastToUnknown 메서드"
ms.assetid: aca47fa0-3c60-47f2-a73c-258f7160adff
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# InterfaceTraits::CastToUnknown 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라구조체를 지원하고 코드에서 직접적으로 사용되는 것을 의도하지 않습니다.  
  
## 구문  
  
```  
template<  
   typename T  
>  
static __forceinline IUnknown* CastToUnknown(  
   _In_ T* ptr  
);  
```  
  
#### 매개 변수  
 `T`  
 `ptr` 매개 변수의 형식입니다.  
  
 `ptr`  
 `T` 형식에 대한 포인터입니다.  
  
## 반환 값  
 `Base` 로부터 파생된 IUknown에 대한 포인터입니다.  
  
## 설명  
 지정된 포인터에 대한 IUnknown 포인터로 캐스팅 .  
  
 `Base` 에 대한 더 자세한 내용은 Public Typedefs 섹션 [InterfaceTraits 구조체](../windows/interfacetraits-structure.md)를 참조하십시오.  
  
## 요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스:** Microsoft::WRL::Details  
  
## 참고 항목  
 [InterfaceTraits 구조체](../windows/interfacetraits-structure.md)   
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)