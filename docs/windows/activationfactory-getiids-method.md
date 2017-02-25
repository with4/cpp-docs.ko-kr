---
title: "ActivationFactory::GetIids 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::ActivationFactory::GetIids"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetIids 메서드"
ms.assetid: 0983d709-d155-4d65-aae4-5b2c8bb0fede
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# ActivationFactory::GetIids 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

구현된 인터페이스 Id의 배열을 검색합니다.  
  
## 구문  
  
```  
STDMETHOD(  
   GetIids  
)(_Out_ ULONG *iidCount, _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids);  
```  
  
#### 매개 변수  
 `iidCount`  
 이 작업이 완료되면, interace Id의 수는 `iids` 배열입니다.  
  
 `iids`  
 이 작업이 완료되면 배열 인터페이스 Id를 구현 합니다.  
  
## 반환 값  
 성공 하면 S\_OK 그렇지 않으면 오류를 설명 하는 HRESULT입니다.  E\_OUTOFMEMORY 는 가능한 실패 HRESULT 입니다.  
  
## 요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [ActivationFactory 클래스](../windows/activationfactory-class.md)