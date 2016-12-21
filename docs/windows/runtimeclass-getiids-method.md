---
title: "RuntimeClass::GetIids 메서드 | Microsoft Docs"
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
  - "implements/Microsoft::WRL::RuntimeClass::GetIids"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetIids 메서드"
ms.assetid: 826a67d1-ebc4-4940-b5d5-7cd66885e4a1
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# RuntimeClass::GetIids 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Id는 현재 RuntimeClass 개체에 의해 구현 된 인터페이스에 포함 될 수 있는 배열을 가져옵니다.  
  
## 구문  
  
```  
STDMETHOD(  
   GetIids  
)  
   (_Out_ ULONG *iidCount,   
   _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids);  
```  
  
#### 매개 변수  
 `iidCount`  
 이 작업이 완료될 때, 배열에 있는 요소의 총 수 `iids`입니다.  
  
 `iids`  
 이 작업이 완료될 때, 인터페이스 Id의 배열에 대한 포인터입니다.  
  
## 반환 값  
 성공 하면 S\_OK 그렇지 않으면 E\_OUTOFMEMORY.  
  
## 요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [RuntimeClass 클래스](../windows/runtimeclass-class.md)