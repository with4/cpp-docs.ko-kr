---
title: "AsyncBase::get_ErrorCode 메서드 | Microsoft Docs"
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
  - "async/Microsoft::WRL::AsyncBase::get_ErrorCode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "get_ErrorCode 메서드"
ms.assetid: 50b4f8a2-9a21-4ea0-bb5d-7ff524d62aea
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# AsyncBase::get_ErrorCode 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

현재 비동기 작업에 대한 오류 코드를 검색 합니다.  
  
## 구문  
  
```  
STDMETHOD(  
   get_ErrorCode  
)(HRESULT* errorCode) override;  
```  
  
#### 매개 변수  
 `errorCode`  
 오류 코드는 현재 저장 된 위치입니다.  
  
## 반환 값  
 성공 하면 S\_OK 그렇지 않으면 비동기 작업이 현재 닫혀 있으면, E\_ILLEGAL\_METHOD\_CALL.  
  
## 요구 사항  
 **헤더:** async.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [AsyncBase 클래스](../windows/asyncbase-class.md)