---
title: "DeferrableEventArgs::InvokeAllFinished 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: 86b45205-3edb-4134-9cd0-ed7a7b4c3b1a
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# DeferrableEventArgs::InvokeAllFinished 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지연된 이벤트를 처리하는 모든 처리가 완료되었음을 나타내기 위해 호출됩니다.  
  
## 구문  
  
```cpp  
void InvokeAllFinished()  
```  
  
## 설명  
 이벤트 소스가 [InvokeAll](../windows/eventsource-invokeall-method.md)을 호출한 후 이 메서드를 호출해야 합니다.  이 메서드를 호출하면 추가 지연이 수행되지 않고, 수행된 지연이 없을 경우 완료 처리기가 강제로 실행됩니다.  
  
 코드 예제는 [DeferrableEventArgs 클래스](../windows/deferrableeventargs-class.md)를 참조하세요.  
  
## 요구 사항  
 **헤더:** event.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [DeferrableEventArgs 클래스](../windows/deferrableeventargs-class.md)   
 [EventSource::InvokeAll 메서드](../windows/eventsource-invokeall-method.md)