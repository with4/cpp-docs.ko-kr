---
title: "EventTargetArray::End 메서드 | Microsoft Docs"
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
  - "event/Microsoft::WRL::Details::EventTargetArray::End"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "End 메서드"
ms.assetid: 20c491b8-f355-4d8f-ad14-8f46121d9af6
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# EventTargetArray::End 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라구조체를 지원하고 코드에서 직접적으로 사용되는 것을 의도하지 않습니다.  
  
## 구문  
  
```  
ComPtr<IUnknown>* End();  
```  
  
## 반환 값  
 이벤트 처리기의 내부 배열에 있는 마지막 요소의 주소입니다.  
  
## 설명  
 이벤트 처리기의 내부 배열에 있는 마지막 요소의 주소를 가져옵니다.  
  
## 요구 사항  
 **헤더:** event.h  
  
 **네임스페이스**Microsoft::WRL::Details  
  
## 참고 항목  
 [EventTargetArray 클래스](../windows/eventtargetarray-class.md)   
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)