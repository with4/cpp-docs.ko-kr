---
title: "AsyncBase::Close 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase::Close"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Close 메서드"
ms.assetid: a52b1124-754b-4393-b491-64aae0c22f1c
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# AsyncBase::Close 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

비동기 작업을 닫습니다.  
  
## 구문  
  
```  
STDMETHOD(  
   Close  
)(void) override;  
```  
  
## 반환 값  
 작업이 닫히거나 이미 닫힌 경우 S\_OK, 그렇지 않으면 E\_ILLEGAL\_STATE\_CHANGE입니다.  
  
## 설명  
 Close\(\), IAsyncInfo::Close의 기본 구현이며 실제로 진행 되지 않습니다.  실제로 비동기 작업을 닫으려면 OnClose\(\) 순수 가상 메서드를 재정의 합니다.  
  
## 요구 사항  
 **헤더:** async.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [AsyncBase 클래스](../windows/asyncbase-class.md)