---
title: "메시지 매핑 | Microsoft Docs"
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
  - "명령 매핑"
  - "명령, 처리기 함수에 연결"
  - "명령, 매핑"
  - "매핑, 명령"
  - "매핑, 메시지"
  - "메시지 처리, 처리기 함수에 연결"
  - "메시지 맵, 메시지 맵 정보"
  - "메시지, 매핑"
ms.assetid: 996f0652-0698-4b8c-b893-cdaa836d9d0f
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# 메시지 매핑
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Each framework class that can receive messages or commands has its own "message map." The framework uses message maps to connect messages and commands to their handler functions.  Any class derived from class `CCmdTarget` can have a message map.  Other articles explain message maps in detail and describe how to use them.  
  
 In spite of the name "message map," message maps handle both messages and commands — all three categories of messages listed in [Message Categories](../mfc/message-categories.md).  
  
## 참고 항목  
 [프레임워크의 메시지 및 명령](../mfc/messages-and-commands-in-the-framework.md)