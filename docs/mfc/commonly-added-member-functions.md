---
title: "일반적으로 추가되는 멤버 함수 | Microsoft Docs"
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
  - "CDialog 클래스, 멤버"
  - "대화 상자 클래스, 일반적으로 추가되는 멤버 함수"
  - "MFC 대화 상자, 컨트롤 알림 메시지"
ms.assetid: f6bd50e8-872a-4039-9996-a85bfccea18d
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 일반적으로 추가되는 멤버 함수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

If your dialog box contains pushbuttons other than OK or Cancel, you need to write message\-handler member functions in your dialog class to respond to the control\-notification messages they generate.  For an example, see the [Scribble](../top/visual-cpp-samples.md) sample program.  You can also handle control\-notification messages from other controls in your dialog box.  
  
## 참고 항목  
 [대화 상자](../mfc/dialog-boxes.md)   
 [대화 상자의 수명 주기](../mfc/life-cycle-of-a-dialog-box.md)   
 [일반적으로 재정의되는 멤버 함수](../mfc/commonly-overridden-member-functions.md)