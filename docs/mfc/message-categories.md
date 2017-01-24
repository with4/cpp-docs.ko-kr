---
title: "메시지 범주 | Microsoft Docs"
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
  - "명령 메시지[C++]"
  - "컨트롤 알림 메시지"
  - "컨트롤[MFC], 알림"
  - "메시지 처리[C++], 메시지 형식"
  - "메시지[C++], 범주"
  - "메시지[C++], Windows"
  - "Windows 메시지[C++], 범주"
ms.assetid: 68e1db75-9da6-4a4d-b2c2-dc4d59f8d87b
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 메시지 범주
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

What kinds of messages do you write handlers for?  There are three main categories:  
  
1.  Windows messages  
  
     This includes primarily those messages beginning with the **WM\_** prefix, except for **WM\_COMMAND**.  Windows messages are handled by windows and views.  These messages often have parameters that are used in determining how to handle the message.  
  
2.  컨트롤 알림  
  
     This includes **WM\_COMMAND** notification messages from controls and other child windows to their parent windows.  For example, an edit control sends its parent a **WM\_COMMAND** message containing the **EN\_CHANGE** control\-notification code when the user has taken an action that may have altered text in the edit control.  The window's handler for the message responds to the notification message in some appropriate way, such as retrieving the text in the control.  
  
     The framework routes control\-notification messages like other **WM\_** messages.  One exception, however, is the **BN\_CLICKED** control\-notification message sent by buttons when the user clicks them.  This message is treated specially as a command message and routed like other commands.  
  
3.  Command messages  
  
     This includes **WM\_COMMAND** notification messages from user\-interface objects: menus, toolbar buttons, and accelerator keys.  The framework processes commands differently from other messages, and they can be handled by more kinds of objects, as explained in [Command Targets](../mfc/command-targets.md).  
  
##  <a name="_core_windows_messages_and_control.2d.notification_messages"></a> Windows Messages and Control\-Notification Messages  
 Messages in categories 1 and 2 — Windows messages and control notifications — are handled by windows: objects of classes derived from class `CWnd`.  This includes `CFrameWnd`, `CMDIFrameWnd`, `CMDIChildWnd`, `CView`, `CDialog`, and your own classes derived from these base classes.  Such objects encapsulate an `HWND`, a handle to a Windows window.  
  
##  <a name="_core_command_messages"></a> 명령 메시지  
 Messages in category 3 — commands — can be handled by a wider variety of objects: documents, document templates, and the application object itself in addition to windows and views.  When a command directly affects some particular object, it makes sense to have that object handle the command.  For example, the Open command on the File menu is logically associated with the application: the application opens a specified document upon receiving the command.  So the handler for the Open command is a member function of the application class.  For more about commands and how they are routed to objects, see [How the Framework Calls a Handler](../mfc/how-the-framework-calls-a-handler.md).  
  
## 참고 항목  
 [프레임워크의 메시지 및 명령](../mfc/messages-and-commands-in-the-framework.md)