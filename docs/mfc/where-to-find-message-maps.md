---
title: "메시지 맵을 찾을 장소 | Microsoft Docs"
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
  - "메시지 맵 찾기"
  - "매크로, 메시지 맵"
  - "메시지 맵, 찾기"
  - "메시지 맵 매크로"
ms.assetid: bf59fbc8-b222-42d3-b5d3-0a79aa3cb923
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 메시지 맵을 찾을 장소
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

When you create a new skeleton application with the Application Wizard, the Application Wizard writes a message map for each command\-target class it creates for you.  This includes your derived application, document, view, and frame\-window classes.  Some of these message maps already have the entries supplied by the Application Wizard for certain messages and predefined commands, and some are just placeholders for handlers that you will add.  
  
 A class's message map is located in the .CPP file for the class.  Working with the basic message maps that the Application Wizard creates, you use the Properties window to add entries for the messages and commands that each class will handle.  A typical message map might look like the following after you add some entries:  
  
 [!code-cpp[NVC_MFCMessageHandling#1](../mfc/codesnippet/CPP/where-to-find-message-maps_1.cpp)]  
  
 The message map consists of a collection of macros.  Two macros, [BEGIN\_MESSAGE\_MAP](../Topic/BEGIN_MESSAGE_MAP.md) and [END\_MESSAGE\_MAP](../Topic/END_MESSAGE_MAP.md), bracket the message map.  Other macros, such as `ON_COMMAND`, fill in the message map's contents.  
  
> [!NOTE]
>  The message\-map macros are not followed by semicolons.  
  
 When you use the Add Class wizard to create a new class, it provides a message map for the class.  Alternatively, you can create a message map manually using the source code editor.  
  
## 참고 항목  
 [프레임워크가 메시지 맵을 검색하는 방법](../mfc/how-the-framework-searches-message-maps.md)