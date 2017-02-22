---
title: "RuntimeClassBaseT::AsIID 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::RuntimeClassBaseT::AsIID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AsIID 메서드"
ms.assetid: 90d7df8a-cf9e-4eef-8837-bc1a25f3fa1a
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# RuntimeClassBaseT::AsIID 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라구조체를 지원하고 코드에서 직접적으로 사용되는 것을 의도하지 않습니다.  
  
## 구문  
  
```  
template<  
   typename T  
>  
__forceinline static HRESULT AsIID(  
   _In_ T* implements,  
   REFIID riid,  
   _Deref_out_ void **ppvObject  
);  
```  
  
#### 매개 변수  
 `T`  
 매개 변수 `riid`로 지정된 인터페이스 ID를 구현하는 형식입니다.  
  
 `implements`  
 템플릿 매개변수 `T`로 지정된 형식의 변수입니다.  
  
 `riid`  
 검색할 인터페이스 ID입니다.  
  
 `ppvObject`  
 이 작업이 성공적이면, 매개변수 `riid`로 지정된 포인터에서 포인터인 인터페이스입니다.  
  
## 반환 값  
 성공 하면 S\_OK 그렇지 않으면 오류를 암시하는 HRESULT입니다.  
  
## 설명  
 지정한 인터페이스ID에 대한 포인터를 검색합니다.  
  
## 요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스**Microsoft::WRL::Details  
  
## 참고 항목  
 [RuntimeClassBaseT 구조체](../windows/runtimeclassbaset-structure.md)   
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)