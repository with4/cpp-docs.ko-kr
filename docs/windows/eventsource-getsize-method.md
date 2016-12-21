---
title: "EventSource::GetSize 메서드 | Microsoft Docs"
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
  - "event/Microsoft::WRL::EventSource::GetSize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetSize 메서드"
ms.assetid: 7825aab5-1a6b-465f-9159-3a6684142d1f
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# EventSource::GetSize 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

현재 EventSource 개체에 연결된 이벤트 처리기 수를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
size_t GetSize() const;  
```  
  
## <a name="return-value"></a>반환 값  
 이벤트 처리기 수 [targets_](../windows/eventsource-targets-data-member.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** event.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [EventSource 클래스](../windows/eventsource-class.md)