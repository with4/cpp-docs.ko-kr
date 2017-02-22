---
title: "EventSource::addRemoveLock_ 데이터 멤버 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "event/Microsoft::WRL::EventSource::addRemoveLock_"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "addRemoveLock_ 데이터 멤버"
ms.assetid: e2d69256-4891-4aad-ad0b-76479c0bb076
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# EventSource::addRemoveLock_ 데이터 멤버
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

에 대 한 액세스를 동기화는 [targets_](../windows/eventsource-targets-data-member.md) 배열을 추가 하는 경우, 제거 또는 이벤트 처리기를 호출 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Wrappers::SRWLock addRemoveLock_;  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** event.h  
  
 **네임스페이스:** Microsoft::WRL
 
 ## <a name="see-also"></a>참고 항목
 [EventSource 클래스](../windows/eventsource-class.md)