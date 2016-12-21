---
title: "사용자 인터페이스 개체 및 명령 ID | Microsoft Docs"
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
  - "명령 처리, 사용자 인터페이스 개체"
  - "명령 ID, 사용자 인터페이스 개체"
  - "명령 라우팅, MFC"
  - "바로 가기 키, ID와 연결"
  - "메뉴 항목, ID와 연결"
  - "MFC, 명령 라우팅"
  - "도구 모음 컨트롤[MFC], 명령 ID"
  - "사용자 인터페이스 개체, ID와 연결"
ms.assetid: 4ea19e9b-ed1e-452e-bd33-7f509107a45b
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 사용자 인터페이스 개체 및 명령 ID
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Menu items, toolbar buttons, and accelerator keys are "user\-interface objects" capable of generating commands.  Each such user\-interface object has an ID.  You associate a user\-interface object with a command by assigning the same ID to the object and the command.  As explained in [Messages](../mfc/messages.md), commands are implemented as special messages.  The figure "Commands in the Framework" below shows how the framework manages commands.  When a user\-interface object generates a command, such as `ID_EDIT_CLEAR_ALL`, one of the objects in your application handles the command — in the figure below, the document object's `OnEditClearAll` function is called via the document's message map.  
  
 ![프레임워크의 명령](../mfc/media/vc385p1.png "vc385P1")  
Framework의 명령  
  
 The figure "Command Updating in the Framework" below shows how MFC updates user\-interface objects such as menu items and toolbar buttons.  Before a menu drops down, or during the idle loop in the case of toolbar buttons, MFC routes an update command.  In the figure below, the document object calls its update command handler, `OnUpdateEditClearAll`, to enable or disable the user\-interface object.  
  
 ![프레임워크에서 명령 업데이트](../mfc/media/vc385p2.png "vc385P2")  
Framework의 명령 업데이트  
  
## 참고 항목  
 [프레임워크의 메시지 및 명령](../mfc/messages-and-commands-in-the-framework.md)