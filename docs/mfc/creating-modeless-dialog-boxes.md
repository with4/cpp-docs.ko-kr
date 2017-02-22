---
title: "모덜리스 대화 상자 만들기 | Microsoft Docs"
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
  - "MFC 대화 상자, 만들기"
  - "MFC 대화 상자, 모덜리스"
  - "모덜리스 대화 상자, 만들기"
ms.assetid: 70d78c7f-3d40-477b-9f78-0f33c359f88b
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# 모덜리스 대화 상자 만들기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

For a modeless dialog box, you must provide your own public constructor in your dialog class.  To create a modeless dialog box, call your public constructor and then call the dialog object's [Create](../Topic/CDialog::Create.md) member function to load the dialog resource.  You can call **Create** either during or after the constructor call.  If the dialog resource has the property **WS\_VISIBLE**, the dialog box appears immediately.  If not, you must call its [ShowWindow](../Topic/CWnd::ShowWindow.md) member function.  
  
## 참고 항목  
 [대화 상자의 수명 주기](../mfc/life-cycle-of-a-dialog-box.md)