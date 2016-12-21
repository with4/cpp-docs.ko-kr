---
title: "클래스에 Windows 메시지 매핑 | Microsoft Docs"
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
  - "매핑, 대화 상자 클래스에 메시지"
  - "메시지 맵[C++], 대화 상자 클래스"
  - "메시지 맵[C++], 클래스에 Windows 메시지 매핑"
  - "대화 상자 클래스에 메시지"
  - "대화 상자 클래스에 메시지, 매핑"
  - "MFC 대화 상자, Windows 메시지"
  - "Windows 메시지[C++], 대화 상자 클래스 매핑"
ms.assetid: a4c6fd1f-1d33-47c9-baa0-001755746d6d
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 클래스에 Windows 메시지 매핑
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

If you need your dialog box to handle Windows messages, override the appropriate handler functions.  To do so, use the Properties window to [map the messages](../mfc/reference/mapping-messages-to-functions.md) to the dialog class.  This writes a message\-map entry for each message and adds the message\-handler member functions to the class.  Use the Visual C\+\+ source code editor to write code in the message handlers.  
  
 You can also override member functions of [CDialog](../mfc/reference/cdialog-class.md) and its base classes, especially [CWnd](../mfc/reference/cwnd-class.md).  
  
## 추가 정보  
  
-   [Message handling and mapping](../mfc/message-handling-and-mapping.md)  
  
-   [Commonly overridden member functions](../mfc/commonly-overridden-member-functions.md)  
  
-   [Commonly added member functions](../mfc/commonly-added-member-functions.md)  
  
## 참고 항목  
 [대화 상자](../mfc/dialog-boxes.md)   
 [대화 상자의 수명 주기](../mfc/life-cycle-of-a-dialog-box.md)