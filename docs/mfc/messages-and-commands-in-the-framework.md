---
title: "프레임워크의 메시지 및 명령 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "이벤트 구동 프로그래밍"
  - "이벤트[C++], MFC의 명령 라우팅"
  - "이벤트[C++], 이벤트 구동 프로그래밍"
  - "메시지 구동 프로그래밍"
ms.assetid: d799ed8c-6a9f-4f05-be5d-29cb5bc6d185
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 프레임워크의 메시지 및 명령
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Applications written for Microsoft Windows are "message driven." In response to events such as mouse clicks, keystrokes, window movements, and so on, Windows sends messages to the proper window.  Framework applications process Windows messages like any other application for Windows.  But the framework also provides some enhancements that make processing messages easier, more maintainable, and better encapsulated.  
  
 The following topics introduce the key terms used in the rest of the article family to discuss messages and commands:  
  
-   [메시지](../mfc/messages.md)  
  
-   [Message handlers](../mfc/message-handlers.md)  
  
-   [Message categories](../mfc/message-categories.md)  
  
-   [Windows messages and control\-notification messages](../mfc/message-categories.md)  
  
-   [Command messages](../mfc/message-categories.md)  
  
-   [메시지 맵](../mfc/mapping-messages.md)  
  
-   [User\-interface objects and command IDs](../mfc/user-interface-objects-and-command-ids.md)  
  
-   [Command targets](../mfc/command-targets.md)  
  
## 참고 항목  
 [메시지 처리 및 매핑](../mfc/message-handling-and-mapping.md)