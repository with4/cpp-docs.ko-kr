---
title: "AsyncBase::Cancel 메서드 | Microsoft Docs"
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
  - "async/Microsoft::WRL::AsyncBase::Cancel"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Cancel 메서드"
ms.assetid: 8bfebc63-3848-4629-bc89-aa538ed7e7ad
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# AsyncBase::Cancel 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

비동기 작업을 취소합니다.  
  
## 구문  
  
```  
STDMETHOD(  
   Cancel  
)(void);  
```  
  
## 반환 값  
 기본적으로 항상 S\_OK를 반환합니다.  
  
## 설명  
 Cancel\(\), IAsyncInfo::Cancel의 기본 구현 이며 실제로 진행 되지 않습니다.  실제로 비동기 작업을 취소 하려면 OnCancel\(\) 순수 가상 메서드를 재정의 합니다.  
  
## 요구 사항  
 **헤더:** async.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [AsyncBase 클래스](../windows/asyncbase-class.md)