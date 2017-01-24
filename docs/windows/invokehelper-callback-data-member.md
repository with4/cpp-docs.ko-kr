---
title: "InvokeHelper::callback_ 데이터 멤버 | Microsoft Docs"
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
  - "event/Microsoft::WRL::Details::InvokeHelper::callback_"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "callback_ 데이터 멤버"
ms.assetid: 6f0cbf6d-0448-46f8-ba71-bd6fd8702e3a
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# InvokeHelper::callback_ 데이터 멤버
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## 구문  
  
```  
TCallback callback_;  
```  
  
## 설명  
 이벤트가 발생할 때 호출할 이벤트 처리기를 나타냅니다.  
  
 `TCallback` 탬플릿 매개변수는 이벤트 처리기의 형식을 지정합니다.  
  
## 요구 사항  
 **헤더:** event.h  
  
 **네임스페이스**Microsoft::WRL::Details  
  
## 참고 항목  
 [InvokeHelper 구조체](../windows/invokehelper-structure.md)   
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)