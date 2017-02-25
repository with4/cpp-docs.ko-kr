---
title: "GetActivationFactory 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Details::GetActivationFactory"
  - "client/ABI::Windows::Foundation::GetActivationFactory"
  - "client/Windows::Foundation::GetActivationFactory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetActivationFactory 함수"
ms.assetid: 5736d285-6beb-42aa-8788-e261c0010afe
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# GetActivationFactory 함수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

템플릿 매개 변수로 지정된 형식에 대한 정품 인증 팩터리를 검색 합니다.  
  
## 구문  
  
```  
template<  
   typename T  
>  
inline HRESULT GetActivationFactory(  
   _In_ HSTRING activatableClassId,  
   _Out_ Microsoft::WRL::Details::ComPtrRef<T> factory  
);  
```  
  
#### 매개 변수  
 `T`  
 정품 팩터리의 형식을 지정하는 템플릿 매개 변수입니다.  
  
 `activatableClassId`  
 정품 공장을 만들 수 있는 클래스의 이름입니다.  
  
 `factory`  
 이 작업이 완료되면, 형식 `T` 에 대한 활성 팩터리 참조.  
  
## 반환 값  
 성공 하면 S\_OK 그렇지 않으면, 이 작업에 실패한 이유를 나타내는 오류입니다.  
  
## 요구 사항  
 **헤더:** client.h  
  
 **네임스페이스**Windows::Foundation  
  
## 참고 항목  
 [Windows::Foundation 네임스페이스](../windows/windows-foundation-namespace.md)