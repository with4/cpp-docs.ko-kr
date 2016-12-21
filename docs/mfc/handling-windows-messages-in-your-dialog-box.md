---
title: "대화 상자에서 Windows 메시지 처리 | Microsoft Docs"
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
  - "메시지 처리[C++], 대화 상자"
  - "MFC 대화 상자, Windows 메시지"
  - "Windows 메시지[C++], 처리"
ms.assetid: 4af0c9cb-09da-4b15-97df-a1cfb89def79
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 대화 상자에서 Windows 메시지 처리
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dialog boxes are windows, so they can handle Windows messages if you supply the appropriate handler functions.  When you create your dialog class with the Add Class Wizard, the wizard adds an empty message map to the class.  Use the Properties window to map any Windows messages or commands you want your class to handle.  
  
 See [Mapping Windows Messages to Your Dialog Class](../mfc/mapping-windows-messages-to-your-class.md) for more information.  
  
## 참고 항목  
 [대화 상자의 수명 주기](../mfc/life-cycle-of-a-dialog-box.md)