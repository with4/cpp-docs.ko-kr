---
title: "AsWeak 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::AsWeak"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AsWeak 함수"
ms.assetid: a6f10cfc-c1d6-4761-adb9-1a119cc99913
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# AsWeak 함수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정된 인스턴스에 대한 약한 참조를 검색합니다.  
  
## 구문  
  
```  
template<  
   typename T  
>  
HRESULT AsWeak(  
   _In_ T* p,  
   _Out_ WeakRef* pWeak  
);  
```  
  
#### 매개 변수  
 `T`  
 매개변수 `p`의 형식에 대한 포인터.  
  
 `p`  
 형식의 인스턴스입니다.  
  
 `pWeak`  
 이 작업이 완료되면, 약한 참조 매개 변수 `p` 에 대한 포인터입니다.  
  
## 반환 값  
 이 작업에 성공 하면 S\_OK 그렇지 않은 경우 실패의 원인을 나타내는 오류입니다.  
  
## 요구 사항  
 **헤더:** client.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)