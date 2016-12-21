---
title: "MessageHandler | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MessageHandler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MessageHandler function"
ms.assetid: 8a0acf97-1b0d-4226-91b9-75446634a03c
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MessageHandler
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**MessageHandler** 의 두 번째 매개 변수에 의해 식별 된 함수 이름이 있는 `MESSAGE_HANDLER` 메시지 맵의 매크로.  
  
## 구문  
  
```  
  
      LRESULT   
      MessageHandler  
      (  
   UINT uMsg,  
   WPARAM wParam,  
   LPARAM lParam,  
   BOOL& bHandled  
);  
```  
  
#### 매개 변수  
 `uMsg`  
 메시지를 지정합니다.  
  
 `wParam`  
 추가 메시지 관련 정보입니다.  
  
 `lParam`  
 추가 메시지 관련 정보입니다.  
  
 `bHandled`  
 메시지 맵 세트 `bHandled` 에  **TRUE** 전에 `MessageHandler` 라고 합니다.  경우 `MessageHandler` 메시지를 완전히 처리 하지 않는 설정 해야 `bHandled` 에  **FALSE** 필요 합니다 라는 메시지가 더 이상 처리를 나타냅니다.  
  
## 반환 값  
 메시지 처리의 결과입니다.  성공한 경우 0입니다.  
  
## 설명  
 이 메시지 처리기에서 메시지 맵을 사용 하는 예제를 보려면  [MESSAGE\_HANDLER](../Topic/MESSAGE_HANDLER.md).  
  
## 참고 항목  
 [Implementing a Window](../atl/implementing-a-window.md)   
 [Message Maps](../atl/message-maps-atl.md)   
 [WM\_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)