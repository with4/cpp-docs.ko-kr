---
title: "애니메이션 컨트롤이 보내는 알림 | Microsoft Docs"
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
  - "애니메이션 컨트롤[C++], 알림"
  - "CAnimateCtrl 클래스, 알림"
  - "컨트롤[MFC], 애니메이션"
  - "알림, 애니메이션 컨트롤"
ms.assetid: 584f5824-446b-4a1a-85f7-ef61842c8186
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 애니메이션 컨트롤이 보내는 알림
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

An animation control \([CAnimateCtrl](../mfc/reference/canimatectrl-class.md)\) sends two different types of notification messages.  The notifications are sent in the form of [WM\_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) messages.  
  
 The [ACN\_START](http://msdn.microsoft.com/library/windows/desktop/bb761891) message is sent when the animation control has started playing a clip.  The [ACN\_STOP](http://msdn.microsoft.com/library/windows/desktop/bb761893) message is sent when the animation control has finished or stopped playing a clip.  
  
## 참고 항목  
 [CAnimateCtrl 사용](../mfc/using-canimatectrl.md)   
 [컨트롤](../mfc/controls-mfc.md)