---
title: "AsyncBase::TryTransitionToError 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase::TryTransitionToError"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "TryTransitionToError 메서드"
ms.assetid: f6d11c25-1ce3-43f9-af1c-97c4dc0f6f0f
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# AsyncBase::TryTransitionToError 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정된 오류 코드 내부에서 오류 상태를 수정할 수 있는지 여부를 나타냅니다.  
  
## 구문  
  
```  
bool TryTransitionToError(  
   const HRESULT error  
);  
```  
  
#### 매개 변수  
 `error`  
 오류 HRESULT입니다.  
  
## 반환 값  
 내부 오류 상태가 변경된 경우 `true`, 그렇지 않으면 `false`.  
  
## 설명  
 오류 상태가 S\_OK를 이미 설정한 경우에 이 작업은 오류 상태를 수정 합니다.  오류 상태가 이미 오류가 있거나, 취소됬거나, 완료됬거나 또는 닫힌 경우, 이 작업은 효과가 없습니다.  
  
## 요구 사항  
 **헤더:** async.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [AsyncBase 클래스](../windows/asyncbase-class.md)