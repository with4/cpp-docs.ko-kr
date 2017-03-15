---
title: "AsyncBase::OnClose 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase::OnClose"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OnClose 메서드"
ms.assetid: 96766450-c262-4611-8534-7d190b799142
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# AsyncBase::OnClose 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

파생 클래스에서 재정의되는 경우 비동기 작업을 선택합니다.  
  
## 구문  
  
```  
virtual void OnClose(  
   void  
) = 0;  
```  
  
## 요구 사항  
 **헤더:** async.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [AsyncBase 클래스](../windows/asyncbase-class.md)   
 [AsyncBase::Close 메서드](../windows/asyncbase-close-method.md)