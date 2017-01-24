---
title: "명령 ID | Microsoft Docs"
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
  - "명령 ID"
  - "명령 ID, MFC"
ms.assetid: e0171a2b-45b9-41fa-945d-ec2f7602ded0
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 명령 ID
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

A command is fully described by its command ID alone \(encoded in the **WM\_COMMAND** message\).  This ID is assigned to the user\-interface object that generates the command.  Typically, IDs are named for the functionality of the user\-interface object they are assigned to.  
  
 For example, a Clear All item in the Edit menu might be assigned an ID such as **ID\_EDIT\_CLEAR\_ALL**.  The class library predefines some IDs, particularly for commands that the framework handles itself, such as **ID\_EDIT\_CLEAR\_ALL** or `ID_FILE_OPEN`.  You will create other command IDs yourself.  
  
 When you create your own menus in the Visual C\+\+ menu editor, it is a good idea to follow the class library's naming convention as illustrated by `ID_FILE_OPEN`.  [Standard Commands](../mfc/standard-commands.md) explains the standard commands defined by the class library.  
  
## 참고 항목  
 [사용자 인터페이스 개체 및 명령 ID](../mfc/user-interface-objects-and-command-ids.md)