---
title: "Rich Edit 컨트롤에서 보내는 알림 | Microsoft Docs"
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
  - "CRichEditCtrl 클래스, 알림"
  - "메시지, 알림"
  - "알림, CRichEditCtrl에서"
  - "rich edit 컨트롤, 알림"
ms.assetid: eb5304fe-f4f3-4557-9ebf-3095dea383c4
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Rich Edit 컨트롤에서 보내는 알림
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Notification messages report events affecting a rich edit control \([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)\).  They can be processed by the parent window or, using message reflection, by the rich edit control itself.  Rich edit controls support all of the notification messages used with edit controls as well as several additional ones.  You can determine which notification messages a rich edit control sends its parent window by setting its "event mask."  
  
 To set the event mask for a rich edit control, use the [SetEventMask](../Topic/CRichEditCtrl::SetEventMask.md) member function.  You can retrieve the current event mask for a rich edit control by using the [GetEventMask](../Topic/CRichEditCtrl::GetEventMask.md) member function.  
  
 The following paragraphs list several specific notifications and their uses:  
  
-   **EN\_MSGFILTER** Handling the **EN\_MSGFILTER** notification lets a class, either the rich edit control or its parent window, filter all keyboard and mouse input to the control.  The handler can prevent the keyboard or mouse message from being processed or can change the message by modifying the specified [MSGFILTER](http://msdn.microsoft.com/library/windows/desktop/bb787936) structure.  
  
-   **EN\_PROTECTED** Handle the **EN\_PROTECTED** notification message to detect when the user attempts to modify protected text.  To mark a range of text as protected, you can set the protected character effect.  For more information, see [Character Formatting in Rich Edit Controls](../mfc/character-formatting-in-rich-edit-controls.md).  
  
-   **EN\_DROPFILES** You can enable the user to drop files in a rich edit control by processing the **EN\_DROPFILES** notification message.  The specified [ENDROPFILES](http://msdn.microsoft.com/library/windows/desktop/bb787895) structure contains information about the files being dropped.  
  
-   **EN\_SELCHANGE** An application can detect when the current selection changes by processing the **EN\_SELCHANGE** notification message.  The notification message specifies a [SELCHANGE](http://msdn.microsoft.com/library/windows/desktop/bb787952) structure containing information about the new selection.  
  
## 참고 항목  
 [CRichEditCtrl 사용](../mfc/using-cricheditctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)