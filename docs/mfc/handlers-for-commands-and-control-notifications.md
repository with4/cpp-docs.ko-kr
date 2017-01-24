---
title: "명령 및 컨트롤 알림에 대한 처리기 | Microsoft Docs"
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
  - "명령, 처리기"
  - "컨트롤[MFC], 알림"
  - "함수[C++], 처리기"
  - "처리기"
  - "처리기, 명령"
  - "처리기, 컨트롤 알림"
  - "알림, 컨트롤에 대한 처리기"
ms.assetid: 20f57f4a-f577-4c09-80a2-43faf32a1c2e
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 명령 및 컨트롤 알림에 대한 처리기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

There are no default handlers for commands or control\-notification messages.  Therefore, you are bound only by convention in naming your handlers for these categories of messages.  When you map the command or control notification to a handler, the Properties windows proposes a name based on the command ID or control\-notification code.  You can accept the proposed name, change it, or replace it.  
  
 Convention suggests that you name handlers in both categories for the user\-interface object they represent.  Thus a handler for the Cut command on the Edit menu might be named  
  
 [!code-cpp[NVC_MFCMessageHandling#4](../mfc/codesnippet/CPP/handlers-for-commands-and-control-notifications_1.h)]  
  
 Because the Cut command is so commonly implemented in applications, the framework predefines the command ID for the Cut command as **ID\_EDIT\_CUT**.  For a list of all predefined command IDs, see the file AFXRES.H.  For more information, see [Standard Commands](../mfc/standard-commands.md).  
  
 In addition, convention suggests a handler for the **BN\_CLICKED** notification message from a button labeled "My Button" might be named  
  
 [!code-cpp[NVC_MFCMessageHandling#5](../mfc/codesnippet/CPP/handlers-for-commands-and-control-notifications_2.h)]  
  
 You might assign this command an ID of `IDC_MY_BUTTON` because it is equivalent to an application\-specific user\-interface object.  
  
 Both categories of messages take no arguments and return no value.  
  
## 참고 항목  
 [메시지 처리기 함수 선언](../mfc/declaring-message-handler-functions.md)