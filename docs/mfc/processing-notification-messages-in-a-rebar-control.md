---
title: "Rebar 컨트롤에서 알림 메시지 처리 | Microsoft Docs"
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
  - "CReBarCtrl 클래스, 알림 메시지 보냄"
  - "알림, CReBarCtrl"
  - "RBN_ 알림 메시지"
  - "RBN_ 알림 메시지, 설명"
ms.assetid: 40f43a60-0c18-4d8d-8fab-213a095624f9
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Rebar 컨트롤에서 알림 메시지 처리
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In the parent class of the rebar control, create an `OnChildNotify` handler function with a switch statement for any rebar\-control \(`CReBarCtrl`\) notification messages you want to handle.  Notifications are sent to the parent window when the user drags objects over the rebar control, changes the layout of the rebar bands, deletes bands from the rebar control, and so on.  
  
 The following notification messages can be sent by the rebar control object:  
  
-   **RBN\_AUTOSIZE** Sent by a rebar control \(created with the **RBS\_AUTOSIZE** style\) when the rebar automatically resizes itself.  
  
-   **RBN\_BEGINDRAG** Sent by a rebar control when the user begins dragging a band.  
  
-   **RBN\_CHILDSIZE** Sent by a rebar control when a band's child window is resized.  
  
-   **RBN\_DELETEDBAND** Sent by a rebar control after a band has been deleted.  
  
-   **RBN\_DELETINGBAND** Sent by a rebar control when a band is about to be deleted.  
  
-   **RBN\_ENDDRAG** Sent by a rebar control when the user stops dragging a band.  
  
-   **RBN\_GETOBJECT** Sent by a rebar control \(created with the **RBS\_REGISTERDROP** style\) when an object is dragged over a band in the control.  
  
-   **RBN\_HEIGHTCHANGE** Sent by a rebar control when its height has changed.  
  
-   **RBN\_LAYOUTCHANGED** Sent by a rebar control when the user changes the layout of the control's bands.  
  
 For more information on these notifications, see [Rebar Control Reference](http://msdn.microsoft.com/library/windows/desktop/bb774375) in the [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
## 참고 항목  
 [CReBarCtrl 사용](../mfc/using-crebarctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)