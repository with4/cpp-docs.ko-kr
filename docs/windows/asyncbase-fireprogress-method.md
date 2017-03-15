---
title: "AsyncBase::FireProgress 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase::FireProgress"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "FireProgress 메서드"
ms.assetid: 4512bef6-0ebc-4465-9b8a-4c9dfa82084c
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# AsyncBase::FireProgress 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

현재 진행 중인 이벤트 처리기를 호출합니다.  
  
## 구문  
  
```  
void FireProgress(  
   const typename ProgressTraits::Arg2Type arg  
);  
```  
  
#### 매개 변수  
 `arg`  
 호출하는 이벤트 핸들러 메서드.  
  
## 설명  
 `ProgressTraits`는 [ArgTraitsHelper 구조체](../windows/argtraitshelper-structure.md)에서 파생됩니다.  
  
## 요구 사항  
 **헤더:** async.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [AsyncBase 클래스](../windows/asyncbase-class.md)