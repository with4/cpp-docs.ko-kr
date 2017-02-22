---
title: "AsyncBase::Start 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase::Start"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Start 메서드"
ms.assetid: 67405c9d-0d1a-4c1e-8ea4-6ba01c1f90d9
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# AsyncBase::Start 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

비동기 작업을 시작합니다.  
  
## 구문  
  
```  
STDMETHOD(  
   Start  
)(void);  
```  
  
## 반환 값  
 작업이 시작 되거나 이미 시작된 경우 S\_OK, 그렇지 않으면 E\_ILLEGAL\_STATE\_CHANGE입니다.  
  
## 설명  
 Start \(\), IAsyncInfo::Start의 기본 구현이며 실제로 진행 되지 않습니다.  실제로 비동기 작업을 시작 하려면 OnStart\(\) 순수 가상 메서드를 재정의 합니다.  
  
## 요구 사항  
 **헤더:** async.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [AsyncBase 클래스](../windows/asyncbase-class.md)