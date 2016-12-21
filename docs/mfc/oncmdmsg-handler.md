---
title: "OnCmdMsg 처리기 | Microsoft Docs"
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
  - "OnCmdMsg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "명령 라우팅, OnCmdMsg 처리기"
  - "처리기"
  - "처리기, OnCmdMessage"
  - "메시지, 라우팅"
  - "OnCmdMessage 메서드"
ms.assetid: 8df07024-506f-47e7-bba9-1c3bc5ad8ab6
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OnCmdMsg 처리기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

To accomplish the routing of commands, each command target calls the `OnCmdMsg` member function of the next command target in the sequence.  Command targets use `OnCmdMsg` to determine whether they can handle a command and to route it to another command target if they cannot handle it.  
  
 Each command\-target class may override the `OnCmdMsg` member function.  The overrides let each class route commands to a particular next target.  A frame window, for example, always routes commands to its current child window or view, as shown in the table [Standard Command Route](../mfc/command-routing.md).  
  
 The default `CCmdTarget` implementation of `OnCmdMsg` uses the message map of the command\-target class to search for a handler function for each command message it receives — in the same way that standard messages are searched.  If it finds a match, it calls the handler.  Message\-map searching is explained in [How the Framework Searches Message Maps](../mfc/how-the-framework-searches-message-maps.md).  
  
## 참고 항목  
 [프레임워크가 처리기를 호출하는 방법](../mfc/how-the-framework-calls-a-handler.md)