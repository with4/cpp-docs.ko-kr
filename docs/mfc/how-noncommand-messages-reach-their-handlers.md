---
title: "명령이 아닌 메시지가 해당 처리기에 도달하는 방법 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "메시지 처리[C++], 비명령 메시지"
  - "메시지[C++], 라우팅"
  - "비명령 메시지"
  - "Windows 메시지[C++], 라우팅"
ms.assetid: e7df8aef-9fae-41f4-9c11-881d8465f602
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# 명령이 아닌 메시지가 해당 처리기에 도달하는 방법
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unlike commands, standard Windows messages do not get routed through a chain of command targets but are usually handled by the window to which Windows sends the message.  The window might be a main frame window, an MDI child window, a standard control, a dialog box, a view, or some other kind of child window.  
  
 At run time, each Windows window is attached to a window object \(derived directly or indirectly from `CWnd`\) that has its own associated message map and handler functions.  The framework uses the message map — as for a command — to map incoming messages to handlers.  
  
## 참고 항목  
 [프레임워크가 처리기를 호출하는 방법](../mfc/how-the-framework-calls-a-handler.md)