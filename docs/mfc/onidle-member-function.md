---
title: "OnIdle 멤버 함수 | Microsoft Docs"
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
  - "OnIdle"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWinApp 클래스, OnIdle 메서드"
  - "유휴 루프 처리"
  - "메시지 처리, OnIdle 메서드"
  - "OnIdle 메서드"
  - "메시지 처리"
ms.assetid: 51adc874-0075-4f76-be1c-79283f46c10b
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OnIdle 멤버 함수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

When no Windows messages are being processed, the framework calls the [CWinApp](../mfc/reference/cwinapp-class.md) member function [OnIdle](../Topic/CWinApp::OnIdle.md) \(described in the MFC Library Reference\).  
  
 Override `OnIdle` to perform background tasks.  The default version updates the state of user\-interface objects such as toolbar buttons and performs cleanup of temporary objects created by the framework in the course of its operations.  The following figure illustrates how the message loop calls `OnIdle` when there are no messages in the queue.  
  
 ![메시지 루프 프로세스](../mfc/media/vc387c1.png "vc387C1")  
메시지 루프  
  
 For more information about what you can do in the idle loop, see [Idle Loop Processing](../mfc/idle-loop-processing.md).  
  
## 참고 항목  
 [CWinApp: 응용 프로그램 클래스](../mfc/cwinapp-the-application-class.md)