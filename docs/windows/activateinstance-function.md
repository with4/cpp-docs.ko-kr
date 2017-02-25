---
title: "ActivateInstance 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Windows::Foundation::ActivateInstance"
  - "client/ABI::Windows::Foundation::ActivateInstance"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActivateInstance 함수"
ms.assetid: 8cfd1dd9-5fda-4cc2-acf8-d40e783b3875
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# ActivateInstance 함수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

등록하고 지정된 클래스 ID에 정의된 지정된 형식의 인스턴스를 검색합니다.  
  
## 구문  
  
```  
template<  
   typename T  
>  
inline HRESULT ActivateInstance(  
   _In_ HSTRING activatableClassId,  
   _Out_ Microsoft::WRL::Details::ComPtrRef<T> instance  
);  
```  
  
#### 매개 변수  
 `T`  
 활성화할 형식입니다.  
  
 `activatableClassId`  
 매개변수 `T` 를 정의하는 클래스 ID의 이름입니다.  
  
 `instance`  
 이 작업이 완료될 때, `T` 의 인스턴스에 대하여 참조합니다.  
  
## 반환 값  
 성공 하면 S\_OK 그렇지 않으면 오류는 오류를 나타내는 HRESULT입니다.  
  
## 요구 사항  
 **헤더:** client.h  
  
 **네임스페이스**Windows::Foundation  
  
## 참고 항목  
 [Windows::Foundation 네임스페이스](../windows/windows-foundation-namespace.md)