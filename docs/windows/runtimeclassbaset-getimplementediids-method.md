---
title: "RuntimeClassBaseT::GetImplementedIIDS 메서드 | Microsoft Docs"
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
  - "implements/Microsoft::WRL::Details::RuntimeClassBaseT::GetImplementedIIDS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetImplementedIIDS 메서드"
ms.assetid: adae54da-521d-4add-87f5-242fbd85f33b
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# RuntimeClassBaseT::GetImplementedIIDS 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라구조체를 지원하고 코드에서 직접적으로 사용되는 것을 의도하지 않습니다.  
  
## 구문  
  
```  
template<  
   typename T  
>  
__forceinline static HRESULT GetImplementedIIDS(  
   _In_ T* implements,  
   _Out_ ULONG *iidCount,  
   _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids  
);  
```  
  
#### 매개 변수  
 `T`  
 `implements` 매개 변수의 형식입니다.  
  
 `implements`  
 매개변수 `T` 로 지정된 형식에 대한 포인터입니다.  
  
 `iidCount`  
 최대 인터페이스 Id 검색 합니다.  
  
 `iids`  
 이 작업이 성공적으로 완료된 경우, 형식 `T` 에 의해 구현된 인터페이스 ID의 배열입니다.  
  
## 반환 값  
 성공 하면 S\_OK 그렇지 않으면 오류를 암시하는 HRESULT입니다.  
  
## 설명  
 Id가 지정된 형식에 의해 구현되는 인터페이스의 배열을 검색합니다.  
  
## 요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스:** Microsoft::WRL::Details  
  
## 참고 항목  
 [RuntimeClassBaseT 구조체](../windows/runtimeclassbaset-structure.md)