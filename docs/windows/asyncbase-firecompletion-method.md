---
title: "AsyncBase::FireCompletion 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase::FireCompletion"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "FireCompletion 메서드"
ms.assetid: b5e29d6d-52e7-4148-a7f3-a313b1359819
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# AsyncBase::FireCompletion 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

완료 이벤트 처리기를 호출하거나 대리자 내부 진행으로 다시 설정합니다.  
  
## 구문  
  
```  
void FireCompletion(  
   void  
) override;  
  
virtual void FireCompletion();  
```  
  
## 설명  
 FireCompletion\(\)의 첫 번째 버전 내부 진행 대리자 변수를 다시 설정합니다.  비동기 작업이 완료되면 완료 이벤트 처리기를 호출하는 두 번째 버전입니다.  
  
## 요구 사항  
 **헤더:** async.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [AsyncBase 클래스](../windows/asyncbase-class.md)