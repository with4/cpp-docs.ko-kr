---
title: "AsyncBase::ContinueAsyncOperation 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase::ContinueAsyncOperation"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ContinueAsyncOperation 메서드"
ms.assetid: ce38181d-2fc3-4579-b0ce-237a3c7648bc
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# AsyncBase::ContinueAsyncOperation 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

비동기 작업 처리를 계속 중지해야 하는지 여부를 결정 합니다.  
  
## 구문  
  
```  
inline bool ContinueAsyncOperation();  
```  
  
## 반환 값  
 비동기 작업의 현재 상태가 *started* 인 경우, `true`, 이는 작업이 계속됨을 의미합니다.  그렇지 않으면 `false`, 즉, 작업을 중단 해야 합니다.  
  
## 요구 사항  
 **헤더:** async.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [AsyncBase 클래스](../windows/asyncbase-class.md)