---
title: "명령 라우팅 설명 | Microsoft Docs"
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
  - "명령 처리, 명령 라우팅"
  - "명령 라우팅, OnCmdMsg 처리기"
  - "MFC, 명령 라우팅"
ms.assetid: 4b7b4741-565f-4878-b076-fd85c670f87f
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 명령 라우팅 설명
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

To illustrate, consider a command message from a Clear All menu item in an MDI application's Edit menu.  Suppose the handler function for this command happens to be a member function of the application's document class.  Here's how that command reaches its handler after the user chooses the menu item:  
  
1.  The main frame window receives the command message first.  
  
2.  The main MDI frame window gives the currently active MDI child window a chance to handle the command.  
  
3.  The standard routing of an MDI child frame window gives its view a chance at the command before checking its own message map.  
  
4.  The view checks its own message map first and, finding no handler, next routes the command to its associated document.  
  
5.  The document checks its message map and finds a handler.  This document member function is called and the routing stops.  
  
 If the document did not have a handler, it would next route the command to its document template.  Then the command would return to the view and then the frame window.  Finally, the frame window would check its message map.  If that check failed as well, the command would be routed back to the main MDI frame window and then to the application object — the ultimate destination of unhandled commands.  
  
## 참고 항목  
 [프레임워크가 처리기를 호출하는 방법](../mfc/how-the-framework-calls-a-handler.md)