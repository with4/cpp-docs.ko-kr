---
title: "EventTargetArray::Begin 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "event/Microsoft::WRL::Details::EventTargetArray::Begin"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Begin 메서드"
ms.assetid: 1cc7fdfd-a2c4-4b28-93cf-1c82842294ba
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# EventTargetArray::Begin 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## 구문  
  
```  
ComPtr<IUnknown>* Begin();  
```  
  
## 반환 값  
 이벤트 처리기의 내부 배열에 있는 첫 번째 요소의 주소입니다.  
  
## 설명  
 이벤트 처리기의 내부 배열에 있는 첫 번째 요소의 주소를 가져옵니다.  
  
## 요구 사항  
 **헤더:** event.h  
  
 **네임스페이스**Microsoft::WRL::Details  
  
## 참고 항목  
 [EventTargetArray 클래스](../windows/eventtargetarray-class.md)   
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)