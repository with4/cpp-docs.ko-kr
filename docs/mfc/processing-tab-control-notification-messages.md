---
title: "탭 컨트롤 알림 메시지 처리 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "CTabCtrl 클래스, 알림 처리"
  - "알림, CTabCtrl에서 처리"
  - "알림, tab 컨트롤"
  - "알림 처리"
  - "tab 컨트롤, 알림 처리"
ms.assetid: 758ccb7a-9e73-48f8-9073-23f7cb09918c
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 탭 컨트롤 알림 메시지 처리
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

As users click tabs or buttons, the tab control \([CTabCtrl](../mfc/reference/ctabctrl-class.md)\) sends notification messages to its parent window.  Handle these messages if you want to do something in response.  For example, when the user clicks a tab, you may want to preset control data on the page prior to displaying it.  
  
 Process **WM\_NOTIFY** messages from the tab control in your view or dialog class.  Use the Properties window to create an [OnChildNotify](../Topic/CWnd::OnChildNotify.md) handler function with a switch statement based on which notification message is being handled.  For a list of the notifications a tab control can send to its parent window, see the **Notifications** section of [Tab Control Reference](http://msdn.microsoft.com/library/windows/desktop/bb760548) in the [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
## 참고 항목  
 [CTabCtrl 사용](../mfc/using-ctabctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)