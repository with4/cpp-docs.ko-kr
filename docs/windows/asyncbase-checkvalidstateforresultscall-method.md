---
title: "AsyncBase::CheckValidStateForResultsCall 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase::CheckValidStateForResultsCall"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CheckValidStateForResultsCall 메서드"
ms.assetid: 87ca6805-bff1-4063-b855-6dd26132deff
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# AsyncBase::CheckValidStateForResultsCall 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

현재 비동기 상태에서 비동기 작업의 결과를 수집할 수 있는지 여부를 테스트 합니다.  
  
## 구문  
  
```  
inline HRESULT CheckValidStateForResultsCall();  
```  
  
## 반환 값  
 결과를 수집할 수 있는 경우 S\_OK, 그렇지 않으면 E\_ILLEGAL\_METHOD\_CALLE\_ILLEGAL\_METHOD\_CALL입니다.  
  
## 요구 사항  
 **헤더:** async.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [AsyncBase 클래스](../windows/asyncbase-class.md)