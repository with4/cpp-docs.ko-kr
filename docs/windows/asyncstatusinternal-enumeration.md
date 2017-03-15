---
title: "AsyncStatusInternal 열거형 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::Details::AsyncStatusInternal"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AsyncStatusInternal 열거형"
ms.assetid: b783923f-3f1c-4487-9384-be572cbc62d7
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# AsyncStatusInternal 열거형
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라구조체를 지원하고 코드에서 직접적으로 사용되는 것을 의도하지 않습니다.  
  
## 구문  
  
```  
enum AsyncStatusInternal;  
```  
  
## 설명  
 비동기 작업의 상태에 대한 내부적 열거형과 **Windows::Foundation::AsyncStatus** 열거형 사이 매핑을 지정합니다.  
  
## 멤버  
 `_Created`  
 동일:: Windows::Foundation::AsyncStatus:: 작성  
  
 `_Started`  
 동일:: Windows::Foundation::AsyncStatus::Started 작성  
  
 `_Completed`  
 동일:: Windows::Foundation::AsyncStatus::Completed 작성  
  
 `_Cancelled`  
 동일:: Windows::Foundation::AsyncStatus::SCancelled 작성  
  
 `_Error`  
 동일:: Windows::Foundation::AsyncStatus::Error 작성  
  
## 요구 사항  
 **헤더:** async.h  
  
 **네임스페이스:** Microsoft::WRL::Details  
  
## 참고 항목  
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)