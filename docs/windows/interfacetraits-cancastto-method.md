---
title: "InterfaceTraits::CanCastTo 메서드 | Microsoft Docs"
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
  - "implements/Microsoft::WRL::Details::InterfaceTraits::CanCastTo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CanCastTo 메서드"
ms.assetid: 275847cb-69ea-42bf-910f-05ba6ef8b48d
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# InterfaceTraits::CanCastTo 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라구조체를 지원하고 코드에서 직접적으로 사용되는 것을 의도하지 않습니다.  
  
## 구문  
  
```  
  
template<typename T>  
static __forceinline bool CanCastTo(  
   _In_ T* ptr,  
   REFIID riid,  
   _Deref_out_ void **ppv  
);  
  
```  
  
#### 매개 변수  
 `ptr`  
 이름 형식에 대한 포인터입니다.  
  
 `riid`  
 `Base`의 인터페이스 ID  
  
 `ppv`  
 이 작업이 성공한다면, `ppv` 는 `Base`에 의해 지정된 인터페이스를 가르킵니다.  그렇지 않으면, `ppv` 는 `nullptr`로 설정합니다.  
  
## 반환 값  
 이 작업이 성공적이면 `true`, 그리고 `ptr` 가 `Base` 에 대한 포인터를 캐스팅합니다, 그렇지 않으면 `false`.  
  
## 설명  
 지정된 포인터는 `Base` 에 대한 포인터를 캐스팅할 수 있는지에 대한 여부를 설명합니다.  
  
 `Base` 에 대한 더 자세한 내용은 Public Typedefs 섹션 [InterfaceTraits 구조체](../windows/interfacetraits-structure.md)를 참조하십시오.  
  
## 요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스:** Microsoft::WRL::Details  
  
## 참고 항목  
 [InterfaceTraits 구조체](../windows/interfacetraits-structure.md)   
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)