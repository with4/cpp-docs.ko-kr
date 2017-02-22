---
title: "헤더 컨트롤 알림 처리 | Microsoft Docs"
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
  - "CHeaderCtrl 클래스, 알림 처리"
  - "컨트롤[MFC], 헤더"
  - "헤더 컨트롤 알림"
  - "헤더 컨트롤, 알림 처리"
  - "알림, CHeaderCtrl 처리"
ms.assetid: e6c6af7c-d458-4d33-85aa-48014ccde5f6
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 헤더 컨트롤 알림 처리
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In your view or dialog class, use the Properties window to create an [OnChildNotify](../Topic/CWnd::OnChildNotify.md) handler function with a switch statement for any header\-control \([CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)\) notification messages you want to handle \(see [Mapping Messages to Functions](../mfc/reference/mapping-messages-to-functions.md)\).  Notifications are sent to the parent window when the user clicks or double\-clicks a header item, drags a divider between items, and so on.  
  
 The notification messages associated with a header control are listed in [Header Control Reference](http://msdn.microsoft.com/library/windows/desktop/bb775239) in the [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
## 참고 항목  
 [CHeaderCtrl 사용](../mfc/using-cheaderctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)