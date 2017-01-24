---
title: "업데이트 처리기가 호출되는 시점 | Microsoft Docs"
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
  - "명령 라우팅, 업데이트 명령"
  - "명령 라우팅, 업데이트 처리기"
  - "메뉴 항목 사용 안 함"
  - "도구 모음 단추 사용 안 함"
  - "메뉴 항목, 사용"
  - "메뉴[C++], 초기화"
  - "메뉴[C++], 컨텍스트 변경으로 업데이트"
  - "도구 모음 단추[C++], 사용"
  - "도구 모음 컨트롤[MFC], OnIdle 메서드 중 업데이트"
  - "도구 모음[C++], 업데이트"
  - "업데이트 처리기"
  - "업데이트 처리기, 호출"
  - "사용자 인터페이스 개체 업데이트"
ms.assetid: 7359f6b1-4669-477d-bd99-690affed08d9
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 업데이트 처리기가 호출되는 시점
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Suppose the user clicks the mouse in the File menu, which generates a `WM_INITMENUPOPUP` message.  The framework's update mechanism collectively updates all items on the File menu before the menu drops down so the user can see it.  
  
 To do this, the framework routes update commands for all menu items in the pop\-up menu along the standard command routing.  Command targets on the routing have an opportunity to update any menu items by matching the update command with an appropriate message\-map entry \(of the form `ON_UPDATE_COMMAND_UI`\) and calling an "update handler" function.  Thus, for a menu with six menu items, six update commands are sent out.  If an update handler exists for the command ID of the menu item, it is called to do the updating.  If not, the framework checks for the existence of a handler for that command ID and enables or disables the menu item as appropriate.  
  
 If the framework does not find an `ON_UPDATE_COMMAND_UI` entry during command routing, it automatically enables the user\-interface object if there is an `ON_COMMAND` entry somewhere with the same command ID.  Otherwise, it disables the user\-interface object.  Therefore, to ensure that a user\-interface object is enabled, supply a handler for the command the object generates or supply an update handler for it.  See the figure in the topic [User\-Interface Objects and Command IDs](../mfc/user-interface-objects-and-command-ids.md).  
  
 It is possible to disable the default disabling of user\-interface objects.  For more information, see the [m\_bAutoMenuEnable](../Topic/CFrameWnd::m_bAutoMenuEnable.md) member of class `CFrameWnd` in the *MFC Reference*.  
  
 Menu initialization is automatic in the framework, occurring when the application receives a `WM_INITMENUPOPUP` message.  During the idle loop, the framework searches the command routing for button update handlers in much the same way as it does for menus.  
  
## 참고 항목  
 [방법: 사용자 인터페이스 개체 업데이트](../mfc/how-to-update-user-interface-objects.md)