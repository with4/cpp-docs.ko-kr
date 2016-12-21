---
title: "ON_UPDATE_COMMAND_UI 매크로 | Microsoft Docs"
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
  - "ON_UPDATE_COMMAND_UI"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "명령 처리기 매크로"
  - "ON_UPDATE_COMMAND_UI 매크로"
  - "업데이트 처리기"
  - "사용자 인터페이스 개체 업데이트"
ms.assetid: 3e72b50f-4119-4c82-81cf-6e09b132de05
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ON_UPDATE_COMMAND_UI 매크로
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Use the **Properties** window to connect a user\-interface object to a command\-update handler in a command\-target object.  It will automatically connect the user\-interface object's ID to the `ON_UPDATE_COMMAND_UI` macro and create a handler in the object that will handle the update.  See [Mapping Messages to Functions](../mfc/reference/mapping-messages-to-functions.md) for more information.  
  
 For example, to update a Clear All command in your program's Edit menu, use the **Properties** window to add a message\-map entry in the chosen class, a function declaration for a command\-update handler called `OnUpdateEditClearAll` in the class declaration, and an empty function template in the class's implementation file.  The function prototype looks like this:  
  
 [!code-cpp[NVC_MFCDocView#2](../mfc/codesnippet/CPP/on-update-command-ui-macro_1.h)]  
  
 Like all handlers, the function shows the **afx\_msg** keyword.  Like all update handlers, it takes one argument, a pointer to a `CCmdUI` object.  
  
## 참고 항목  
 [방법: 사용자 인터페이스 개체 업데이트](../mfc/how-to-update-user-interface-objects.md)