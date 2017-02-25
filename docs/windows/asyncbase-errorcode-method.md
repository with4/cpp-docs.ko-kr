---
title: "AsyncBase::ErrorCode 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase::ErrorCode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ErrorCode 메서드"
ms.assetid: 3f5f0f69-d60a-4a67-8cc6-a55fdc89a192
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# AsyncBase::ErrorCode 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

현재 비동기 작업에 대한 오류 코드를 검색 합니다.  
  
## 구문  
  
```  
inline void ErrorCode(  
   HRESULT *error  
);  
```  
  
#### 매개 변수  
 `error`  
 이 작업에서 현재 오류 코드를 저장하는 위치는 위치입니다.  
  
## 설명  
 이 작업은 스레드로부터 안전하지 않습니다.  
  
## 요구 사항  
 **헤더:** async.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [AsyncBase 클래스](../windows/asyncbase-class.md)