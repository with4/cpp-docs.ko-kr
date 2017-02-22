---
title: "목록 컨트롤에서 알림 메시지 처리 | Microsoft Docs"
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
  - "CListCtrl 클래스, 알림 처리"
  - "알림 처리"
ms.assetid: 1f0e296e-d2a3-48fc-ae38-51d7fb096f51
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 목록 컨트롤에서 알림 메시지 처리
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

As users click column headers, drag icons, edit labels, and so on, the list control \([CListCtrl](../mfc/reference/clistctrl-class.md)\) sends notification messages to its parent window.  Handle these messages if you want to do something in response.  For example, when the user clicks a column header, you might want to sort the items based on the contents of the clicked column, as in Microsoft Outlook.  
  
 Process **WM\_NOTIFY** messages from the list control in your view or dialog class.  Use the Properties window to create an [OnChildNotify](../Topic/CWnd::OnChildNotify.md) handler function with a switch statement based on which notification message is being handled.  
  
 For a list of the notifications a list control can send to its parent window, see [List View Control Reference](http://msdn.microsoft.com/library/windows/desktop/bb774737) in the [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
## 참고 항목  
 [CListCtrl 사용](../mfc/using-clistctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)